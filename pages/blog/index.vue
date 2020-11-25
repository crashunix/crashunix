<template>
  <div class="pt-10 pb-20">
    <div class="container mx-auto space-y-10">
      <div class="flex justify-between">
        <span>Todos os artigos</span>
        <a @click="filter" class="flex items-center space-x-2">
            <span>Filtrar</span>
            <img class="w-5" src="~assets/icons/filter.svg" alt="filter"/>
        </a>
      </div>
      <div class="grid grid-cols-1 lg:grid-cols-3 gap-10">
        <Article v-for="article in articles" :key="article.slug" :article="article" />
      </div>
    </div>
  </div>
</template>
<script>
export default {
  layout: "detail",
  async asyncData({ $content }) {
    const articles = await $content("articles").limit(4).sortBy().fetch();
    return { articles };
  },
};
</script>