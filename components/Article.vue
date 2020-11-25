<template>
    <nuxt-link class="space-y-3" :to="`/blog/${article.slug}`">
        <img :src="article.image.url" class="object-cover" />
        <p>{{$moment(article.updatedAt).fromNow()}}</p>
        <p class="text-2xl">{{article.title}}</p>
        <p>{{article.subtitle}}</p>
    </nuxt-link>
</template>
<script>
export default {
    props: ['article'],
}
</script>