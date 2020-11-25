<template>
  <div class="pt-10 pb-20">
    <div class="container mx-auto space-y-10">
      <div class="flex justify-between">
        <span>Blog</span>
        <nuxt-link class="flex items-center space-x-2" to="/blog"><span>Todos</span><img class="w-5" src="~assets/icons/arrow-right.svg" alt="todos" /></nuxt-link>
      </div>
      <div class="grid grid-cols-1 lg:grid-cols-3 gap-10">
          <nuxt-link class="space-y-3" v-for="article in articles" :key="article.slug" :to="`/blog/${article.slug}`">
            <img :src="article.image.url" class="object-cover h-64" />
            <p>{{$moment(article.updatedAt).fromNow()}}</p>
            <p class="text-2xl">{{article.title}}</p>
            <p>{{article.subtitle}}</p>
          </nuxt-link>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  props: ["articles"]
}
</script>