<template>
  <div>
    <h1>{{ article.title }}</h1>
    <h2>{{ article.subtitle }}</h2>
    <p>by <span class="font-semibold">{{article.author.username}}</span></p>
    <p>{{ $moment(article.updatedAt).fromNow() }}</p>
    <img :src="article.image.url" :alt="article.image.alt" />
    <nuxt-content :document="article" />
  </div>
</template>
<script>
export default {
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
        @apply text-xl text-gray-800;
    }
</style>