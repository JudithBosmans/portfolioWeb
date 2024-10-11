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
    // Fetch homepage data
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

    // Fetch navigation data
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
  <!-- Main Grid and Content -->
  <div
    class="flex items-center justify-center h-screen overflow-hidden bg-white"
  >
    <div class="grid grid-cols-6 grid-rows-4 gap-14">
      <div
        v-for="(image, index) in images"
        :key="index"
        class="grid-item aspect-square overflow-hidden"
      >
        <img
          :src="image"
          alt="Homepage Image"
          :class="[
            'w-full h-full object-cover animate-flash',
            shouldMakeTransparent(index) ? 'opacity-0' : '',
          ]"
        />
      </div>
    </div>

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

hr {
  opacity: 0.1;
}
</style>
