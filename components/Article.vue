<template>
    <nuxt-link class="space-y-3 transition-colors duration-500 ease-in-out text-black dark:text-white" :to="`/blog/${article.slug}`">
        <img :src="article.image.url" class="object-cover" />
        <p class="transition-colors duration-500 ease-in-out text-gray-500 dark:text-gray-200">{{$moment(article.updatedAt).fromNow()}}</p>
        <p class="text-2xl transition-colors duration-500 ease-in-out text-black dark:text-white">{{article.title}}</p>
        <p class="transition-colors duration-500 ease-in-out text-gray-500 dark:text-gray-200">{{article.subtitle}}</p>
    </nuxt-link>
</template>
<script>
export default {
    props: ['article'],
}
</script>