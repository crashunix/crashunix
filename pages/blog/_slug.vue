<template>
  <div class="pt-10 pb-20">
    <div class="container mx-auto space-y-4">
      <h1 class="text-2xl lg:text-4xl lg:w-3/5 transition-colors duration-500 ease-in-out text-black dark:text-white">{{ article.title }}</h1>
      <p class="transition-colors duration-500 ease-in-out text-gray-600 dark:text-gray-200">{{ $moment(article.updatedAt).fromNow() }}</p>
      <div class="flex items-center space-x-2 transition-colors duration-500 ease-in-out text-gray-600 dark:text-gray-200">
        <p>by <span class="font-semibold">{{ article.author.name }}</span></p>
      </div>
      <img :src="article.image.url" :alt="article.image.alt" />
      <nuxt-content :document="article"></nuxt-content>
    </div>
  </div>
</template>
<script>
export default {
  layout: "detail",
  async asyncData({ $content, params }) {
    const article = await $content("articles", params.slug).fetch();
    return { article };
  },
  data() {
    return {};
  },
};
</script>
<style>
.nuxt-content h2 {
  @apply text-xl font-semibold transition-colors duration-500 ease-in-out text-black dark:text-white;
}
.nuxt-content p {
  @apply my-5 transition-colors duration-500 ease-in-out text-black dark:text-white;
}
</style>