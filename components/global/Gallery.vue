<template>
  <div class="grid grid-cols-4 gap-7 mt-10" id="gallery">
    <div v-for="item in galleryData" :key="item.id" class="text-center p-4">
      <!-- Trigger Button -->
      <label :for="item.id" class="cursor-pointer inline-block rounded-lg">
        <img :src="item.imgSrc" :alt="item.title" class="rounded-lg" />
      </label>

      <!-- Modal Checkbox -->
      <input :id="item.id" type="checkbox" class="hidden modal-state" />

      <!-- Modal -->
      <div
        class="fixed inset-0 opacity-0 invisible transition-opacity duration-200 ease-linear bg-black/90 modal"
      >
        <label
          :for="item.id"
          class="absolute inset-0 cursor-pointer modal__bg"
        ></label>
        <div
          class="absolute top-[-20%] right-0 bottom-0 left-0 w-1/2 h-1/2 p-6 m-auto rounded-lg shadow-md overflow-auto transition-all duration-200 ease-linear modal__inner"
        >
          <label
            :for="item.id"
            class="absolute top-4 right-4 w-4 h-4 cursor-pointer modal__close"
          >
            <span
              class="absolute block w-[2px] h-6 bg-gray-300 rotate-45 top-0 left-1/2 -translate-x-1/2"
            ></span>
            <span
              class="absolute block w-[2px] h-6 bg-gray-300 -rotate-45 top-0 left-1/2 -translate-x-1/2"
            ></span>
          </label>
          <h2 class="text-lg font-semibold text-center">{{ item.title }}</h2>
          <p class="flex items-start">
            <img
              :src="item.gifSrc"
              alt=""
              class="max-w-[200px] h-auto float-left mr-4 mb-4"
            />
            {{ item.description }}
          </p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Gallery",
  data() {
    return {
      galleryData: [
        {
          id: "modal-1",
          title: "Caaaats FTW!",
          description:
            "Aliquam in sagittis nulla. Curabitur euismod diam eget risus venenatis...",
          imgSrc: "/img/work/mockup1.png",
          gifSrc: "https://i.imgur.com/HnrkBwB.gif",
        },
        {
          id: "modal-2",
          title: "More Cats!",
          description:
            "Nunc vel mauris dolor. Class aptent taciti sociosqu ad litora...",
          imgSrc: "/img/work/mockup2.png",
          gifSrc: "https://i.imgur.com/AnotherGif.gif",
        },
      ],
    };
  },
};
</script>

<style scoped>
/* Additional styles if needed */
</style>
