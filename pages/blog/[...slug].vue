<template>
<div>
  <div class="pr-5">
    <Drawer />
  </div>
  <div class="container mx-auto max-w-4xl space-y-6 h-full mb-20 mt-10">
    <NuxtLink to="/blog">
      <span>
        <svg xmlns="http://www.w3.org/2000/svg" width="1em" height="1em" viewBox="0 0 24 24"><path fill="currentColor" d="m6.921 12.5l5.793 5.792L12 19l-7-7l7-7l.714.708L6.92 11.5H19v1z"></path></svg>
      </span>  
      <span class="text-xs">
      back to the blog overview
      </span>
    </NuxtLink>
    <h1 class="text-4xl font-bold">
      {{ post.title }}
    </h1>
    <h4 v-if="post.subtitle" class="text-xl font-bold opacity-80">
      {{ post.subtitle }}
    </h4>
    <ContentDoc />
    <div class="text-xs leading-3">
      <hr> 
      <p v-if="post.date" class="text-xs opacity-50 hover:opacity-100">last updated on: {{ formatDate(post.date) }}
            <span v-if="post.author" class="text-xs">authored by: {{ post.author }} </span>
          </p>
      <p v-if="post.tags"><ArticleTags /></p> 
    </div>
  </div>
</div>  
</template>

<script setup>
const route = useRoute()
const actualPath = route.path.replace(/\/$/, '');

const { data: post } = await useAsyncData(`hello`, () =>
    queryContent(actualPath).findOne()
);

// Function to format the date
function formatDate(date) {
  const options = { year: 'numeric', month: 'long' };
  return new Date(date).toLocaleDateString(undefined, options);
}
</script>