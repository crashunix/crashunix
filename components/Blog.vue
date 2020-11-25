<template>
  <div class="pt-10 pb-20">
    <div class="container mx-auto space-y-10">
      <div class="flex justify-between">
        <span>Blog</span>
        <nuxt-link class="flex items-center space-x-2" to="/blog"><span>Todos</span><img class="w-5" src="~assets/icons/arrow-right.svg" alt="todos" /></nuxt-link>
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