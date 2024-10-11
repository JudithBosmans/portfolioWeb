<template>
  <div class="pr-5">
    <Drawer />
  </div>
  <div class="container mb-20 mt-10 animate-fade animate-once animate-delay-[500ms]"> 
    <div class="mb-10">
      <NuxtLink :to="`/${post._dir}`">
        <span>
          <svg xmlns="http://www.w3.org/2000/svg" width="1em" height="1em" viewBox="0 0 24 24">
            <path fill="currentColor" d="m6.921 12.5l5.793 5.792L12 19l-7-7l7-7l.714.708L6.92 11.5H19v1z"></path>
          </svg>
        </span>  
        <span class="text-xs">Back to pages overview</span>
      </NuxtLink>
    </div>

    <ContentSlot >
      <h1 class="text-4xl font-bold">{{ post.title }}</h1>
      <p class="text-xl opacity-80" >{{ post.description }}</p>
    </ContentSlot>  

    <ContentDoc v-slot="{ doc }">
      <article>
        <ContentRenderer :value="doc" />
      </article>
    </ContentDoc>

    <div v-if="post.imagegallery && post.showgaller !=='false'">
      <ImageGallery />
    </div>


    <div class="text-xs leading-3">
      <hr> 
      <p v-if="post.date" class="text-xs opacity-50 hover:opacity-100">last updated on: {{ formatDate(post.date) }}
            <span v-if="post.author" class="text-xs">authored by: {{ post.author }} </span>
          </p>
      <p v-if="post.tags"><ArticleTags /></p> 
    </div>

  </div>

</template>

<script setup>
import { ref, onMounted } from 'vue';
import { useRoute, useAsyncData } from '#app';

// Define reactive properties for managing image loading state
const imageLoading = ref(true);

// Get the current route
const route = useRoute();
const actualPath = route.path.replace(/\/$/, '');

// Fetch post data
const { data: post } = await useAsyncData('page', () =>
  queryContent(actualPath).findOne()
);


// Format the date
function formatDate(date) {
  const options = { year: 'numeric', month: 'long' };
  return new Date(date).toLocaleDateString(undefined, options);
}
</script>


