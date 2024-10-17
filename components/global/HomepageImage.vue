<script setup>
import { ref, onMounted } from "vue";

// Refs for settings and navigation data
const settings = ref(null);
const isLoading = ref(true);
const hasError = ref(false);
const images = ref([]);
const navigations = ref({});

// Fetch JSON data for homepage
onMounted(async () => {
  try {
    const homepageResponse = await fetch("/_data/homepage.json");
    if (!homepageResponse.ok) {
      throw new Error(`HTTP error! status: ${homepageResponse.status}`);
    }
    const homepageJson = await homepageResponse.json();
    settings.value = homepageJson;

    if (homepageJson.thumbnail && homepageJson.thumbnail.imagesHomepage) {
      const imagesArray = homepageJson.thumbnail.imagesHomepage[0];
      images.value = Object.values(imagesArray);
    }

    const navigationResponse = await fetch("/_data/menus.json");
    if (!navigationResponse.ok) {
      throw new Error(`HTTP error! status: ${navigationResponse.status}`);
    }
    const navigationJson = await navigationResponse.json();
    navigations.value = navigationJson;

    isLoading.value = false;
  } catch (error) {
    hasError.value = true;
    console.error("Error loading settings or navigations:", error);
  }
});

function shouldMakeTransparent(index) {
  const numCols = 6;
  const row = Math.floor(index / numCols);
  const col = index % numCols;

  return row % 2 === 0 ? col % 2 !== 0 : col % 2 === 0;
}
</script>

<template>
  <div class="flex items-center justify-center h-screen overflow-hidden">
    <div class="grid grid-cols-6 grid-rows-4 gap-14 relative z-20">
      <div
        v-for="(image, index) in images"
        :key="index"
        class="grid-item aspect-square overflow-hidden relative"
      >
        <router-link :to="`/page`" v-if="!shouldMakeTransparent(index)">
          <img
            :src="image"
            alt="Homepage Image"
            :class="[
              'w-full h-full object-cover animate-flash',
              shouldMakeTransparent(index) ? 'transparent' : '',
            ]"
            class="z-30"
          />
        </router-link>
        <!-- Add an image without router-link but transparent and with no pointer events -->
        <img
          v-else
          :src="image"
          alt="Transparent Image"
          :class="[
            'w-full h-full object-cover animate-flash pointer-none opacity-0',
          ]"
          class="z-30"
        />
      </div>
    </div>

    <!-- Overlay content, pushed to the back with lower z-index -->
    <div
      class="z-10 absolute flex flex-col justify-center items-center h-full w-full"
    >
      <div v-if="isLoading" class="flex items-center justify-center w-full">
        <p>Loading...</p>
      </div>

      <div v-else-if="hasError" class="flex items-center justify-center w-full">
        <p>Error loading homepage images. Please try again later.</p>
      </div>

      <div
        v-else-if="settings && settings.thumbnail"
        class="text-center p-4 lg:p-20"
      >
        <h1 class="text-4xl font-bold">{{ settings.homepage_title }}</h1>
        <h2 class="text-lg mt-3">{{ settings.homepage_subtitle }}</h2>
        <p class="text-sm opacity-80">{{ settings.body }}</p>
      </div>

      <div v-else>
        <p>No thumbnail available.</p>
      </div>
    </div>
  </div>
</template>

<style scoped>
.grid-item {
  overflow: hidden;
  position: relative;
}

.image {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.w-full.h-full.object-cover.animate-flash:hover {
  transform: scale(1.2);
  transition: transform 0.2s;
}
</style>
