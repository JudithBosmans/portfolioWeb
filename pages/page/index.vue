<template>
  <div>
    <div
      class="absolute inset-x-0 -top-40 -z-10 transform-gpu overflow-hidden blur-3xl sm:-top-80"
      aria-hidden="true"
    >
      <div
        class="relative left-[calc(50%-11rem)] aspect-[1155/678] w-[36.125rem] -translate-x-1/2 rotate-[30deg] bg-gradient-to-tr from-[#ff6262] to-[#f6a83b] opacity-45 sm:left-[calc(50%-30rem)] sm:w-[72.1875rem]"
        style="
          clip-path: polygon(
            74.1% 44.1%,
            100% 61.6%,
            97.5% 26.9%,
            85.5% 0.1%,
            80.7% 2%,
            72.5% 32.5%,
            60.2% 62.4%,
            52.4% 68.1%,
            47.5% 58.3%,
            45.2% 34.5%,
            27.5% 76.7%,
            0.1% 64.9%,
            17.9% 100%,
            27.6% 76.8%,
            76.1% 97.7%,
            74.1% 44.1%
          );
        "
      ></div>
    </div>
    <div
      class="absolute inset-x-0 -top-80 -z-10 transform-gpu overflow-hidden blur-2xl"
      aria-hidden="true"
    >
      <div
        class="relative aspect-[1155/678] right-0 w-[40] -translate-x-1/2 rotate-[80deg] bg-gradient-to-tr from-[#ff6565] to-[#f6a83b] opacity-45"
        style="
          clip-path: polygon(
            74.1% 44.1%,
            100% 61.6%,
            97.5% 26.9%,
            85.5% 0.1%,
            80.7% 2%,
            72.5% 32.5%,
            60.2% 62.4%,
            52.4% 68.1%,
            47.5% 58.3%,
            45.2% 34.5%,
            27.5% 76.7%,
            0.1% 64.9%,
            17.9% 100%,
            27.6% 76.8%,
            76.1% 97.7%,
            74.1% 44.1%
          );
        "
      ></div>
    </div>
    <div class="pr-5">
      <Drawer />
    </div>

    <!------------
     ABOUT SECTION 
     ------------>
    <main class="mx-auto max-w-7xl space-y-6 px-6 lg:px-12 mt-[15%] mb-[20%]">
      <div>
        <section class="w-full py-6 md:py-12 lg:py-16">
          <div
            class="flex flex-col items-center justify-center gap-10 md:flex-row md:items-start lg:gap-12"
          >
            <!-- Image Section with Defined Width -->
            <div
              class="flex items-center mr-[15vw] gap-4 w-full md:w-1/3 lg:w-1/4 flex-shrink-0"
            >
              <!-- Prevent shrinking on larger screens -->
              <img
                src="/img/about/about.jpeg"
                alt="Profile Picture"
                class="rounded-full w-28 h-28 object-cover object-center mr-10 animate-spin"
              />
              <div class="space-y-2">
                <h2
                  class="text-3xl font-bold tracking-wider sm:text-4xl lg:text-5xl leading-none"
                >
                  Judith Bosmans
                </h2>
                <p class="text-gray-500 dark:text-gray-400 text-black">
                  Frontend Developer
                </p>
              </div>
            </div>

            <!-- Description Section -->
            <div
              class="flex flex-col space-y-2 md:space-y-4 w-full md:flex-grow"
            >
              <p class="text-black md:text-xl leading-relaxed">
                Passionate about creating beautiful and interactive web
                experiences. I love turning complex problems into simple and
                intuitive designs. My goal is to build products that provide
                value and delight to the users.
              </p>
              <!-- Skills List -->
              <ul
                class="grid grid-cols-2 gap-4 text-sm font-medium md:grid-cols-3 md:text-base lg:gap-1 text-prettyRed"
              >
                <li class="flex items-center space-x-2">
                  <svg
                    class="w-6 h-6 text-gray-800 mr-2 text-prettyRed"
                    aria-hidden="true"
                    xmlns="http://www.w3.org/2000/svg"
                    width="24"
                    height="24"
                    fill="none"
                    viewBox="0 0 24 24"
                  >
                    <path
                      stroke="currentColor"
                      stroke-linecap="round"
                      stroke-linejoin="round"
                      stroke-width="2"
                      d="M8.5 11.5 11 14l4-4m6 2a9 9 0 1 1-18 0 9 9 0 0 1 18 0Z"
                    />
                  </svg>
                  HTML
                </li>
                <li class="flex items-center space-x-2">
                  <svg
                    class="w-6 h-6 text-gray-800 mr-2 text-prettyRed"
                    aria-hidden="true"
                    xmlns="http://www.w3.org/2000/svg"
                    width="24"
                    height="24"
                    fill="none"
                    viewBox="0 0 24 24"
                  >
                    <path
                      stroke="currentColor"
                      stroke-linecap="round"
                      stroke-linejoin="round"
                      stroke-width="2"
                      d="M8.5 11.5 11 14l4-4m6 2a9 9 0 1 1-18 0 9 9 0 0 1 18 0Z"
                    />
                  </svg>
                  CSS
                </li>
                <li class="flex items-center space-x-2">
                  <svg
                    class="w-6 h-6 text-gray-800 mr-2 text-prettyRed"
                    aria-hidden="true"
                    xmlns="http://www.w3.org/2000/svg"
                    width="24"
                    height="24"
                    fill="none"
                    viewBox="0 0 24 24"
                  >
                    <path
                      stroke="currentColor"
                      stroke-linecap="round"
                      stroke-linejoin="round"
                      stroke-width="2"
                      d="M8.5 11.5 11 14l4-4m6 2a9 9 0 1 1-18 0 9 9 0 0 1 18 0Z"
                    />
                  </svg>
                  JS
                </li>
                <li class="flex items-center space-x-2">
                  <svg
                    class="w-6 h-6 text-gray-800 mr-2 text-prettyRed"
                    aria-hidden="true"
                    xmlns="http://www.w3.org/2000/svg"
                    width="24"
                    height="24"
                    fill="none"
                    viewBox="0 0 24 24"
                  >
                    <path
                      stroke="currentColor"
                      stroke-linecap="round"
                      stroke-linejoin="round"
                      stroke-width="2"
                      d="M8.5 11.5 11 14l4-4m6 2a9 9 0 1 1-18 0 9 9 0 0 1 18 0Z"
                    />
                  </svg>
                  REACT, VUE, ...
                </li>
                <li class="flex items-center space-x-2">
                  <svg
                    class="w-6 h-6 text-gray-800 mr-2 text-prettyRed"
                    aria-hidden="true"
                    xmlns="http://www.w3.org/2000/svg"
                    width="24"
                    height="24"
                    fill="none"
                    viewBox="0 0 24 24"
                  >
                    <path
                      stroke="currentColor"
                      stroke-linecap="round"
                      stroke-linejoin="round"
                      stroke-width="2"
                      d="M8.5 11.5 11 14l4-4m6 2a9 9 0 1 1-18 0 9 9 0 0 1 18 0Z"
                    />
                  </svg>
                  ADOBE SUITE
                </li>
                <li class="flex items-center space-x-2">
                  <svg
                    class="w-6 h-6 text-gray-800 mr-2 text-prettyRed"
                    aria-hidden="true"
                    xmlns="http://www.w3.org/2000/svg"
                    width="24"
                    height="24"
                    fill="none"
                    viewBox="0 0 24 24"
                  >
                    <path
                      stroke="currentColor"
                      stroke-linecap="round"
                      stroke-linejoin="round"
                      stroke-width="2"
                      d="M8.5 11.5 11 14l4-4m6 2a9 9 0 1 1-18 0 9 9 0 0 1 18 0Z"
                    />
                  </svg>
                  MAYA
                </li>
                <li class="flex items-center space-x-2">
                  <svg
                    class="w-6 h-6 text-gray-800 mr-2 text-prettyRed"
                    aria-hidden="true"
                    xmlns="http://www.w3.org/2000/svg"
                    width="24"
                    height="24"
                    fill="none"
                    viewBox="0 0 24 24"
                  >
                    <path
                      stroke="currentColor"
                      stroke-linecap="round"
                      stroke-linejoin="round"
                      stroke-width="2"
                      d="M8.5 11.5 11 14l4-4m6 2a9 9 0 1 1-18 0 9 9 0 0 1 18 0Z"
                    />
                  </svg>
                  UX/UI
                </li>
                <li class="flex items-center space-x-2">
                  <svg
                    class="w-6 h-6 text-gray-800 mr-2 text-prettyRed"
                    aria-hidden="true"
                    xmlns="http://www.w3.org/2000/svg"
                    width="24"
                    height="24"
                    fill="none"
                    viewBox="0 0 24 24"
                  >
                    <path
                      stroke="currentColor"
                      stroke-linecap="round"
                      stroke-linejoin="round"
                      stroke-width="2"
                      d="M8.5 11.5 11 14l4-4m6 2a9 9 0 1 1-18 0 9 9 0 0 1 18 0Z"
                    />
                  </svg>
                  GROWTH MINDSET
                </li>
              </ul>
            </div>
          </div>
        </section>
      </div>
    </main>

    <!------------
     PROJECTS 
     ------------>
    <main class="mx-auto max-w-4xl space-y-6 px-4 mt-20">
      <div class="text-4xl">PROJECTS</div>
      <div class="text-s">Enough about, take a look at what I've made.</div>
      <div class="masonry">
        <div class="masonry-item" v-for="post in posts" :key="post.slug">
          <div class="masonry-image">
            <NuxtImg
              :src="post.thumbnail"
              alt="Post thumbnail"
              class="w-full h-64 object-cover rounded-md mb-4"
              :width="750"
              :height="550"
            />
          </div>
          <NuxtLink :to="post._path" class="block">
            <div class="masonry-item-text p-4">
              <h2 class="text-xl mb-2">{{ post.title }}</h2>
              <p v-if="post.description" class="text-gray-600 line-clamp-3">
                {{ post.description }}
              </p>
              <ClientOnly>
                <article v-if="post.tags" class="text-xs mt-2">
                  <li
                    v-for="(item, index) in post.tags"
                    :key="index"
                    class="inline mr-2"
                  >
                    <NuxtLink :to="`/tags/${item}`">{{ item }}</NuxtLink>
                  </li>
                </article>
              </ClientOnly>
            </div>
          </NuxtLink>
        </div>
      </div>
    </main>
  </div>
</template>

<script setup>
const { data: posts } = await useAsyncData("posts", () => {
  return queryContent("/page")
    .sort({ promoted: 1 })

    .find();
});
</script>
