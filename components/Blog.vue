<template>
  <div class="pt-10 pb-20">
    <div class="container mx-auto space-y-10">
      <div class="flex justify-between">
        <span class="transition-colors duration-500 ease-in-out text-black dark:text-white">Blog</span>
        <nuxt-link class="flex items-center space-x-2 transition-colors duration-500 ease-in-out text-black dark:text-white" to="/projects">
          <span>Todos</span>
          <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="feather feather-arrow-right transition-colors duration-500 ease-in-out text-black dark:text-white"><line x1="5" y1="12" x2="19" y2="12"></line><polyline points="12 5 19 12 12 19"></polyline></svg>
        </nuxt-link>
      </div>
      <div class="grid grid-cols-1 lg:grid-cols-3 gap-10">
        <Article v-for="article in articles" :key="article.slug" :article="article" />
      </div>
    </div>
  </div>
</template>
<script>
export default {
  props: ["articles"]
}
</script>