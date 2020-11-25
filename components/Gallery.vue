<template>
  <div class="pt-10 pb-20">
    <div class="container mx-auto space-y-10">
      <div class="flex justify-between">
        <span>Galeria</span>
        <nuxt-link class="flex items-center space-x-2" to="/projects"><span>Todos</span><img class="w-5" src="~assets/icons/arrow-right.svg" alt="todos" /></nuxt-link>
      </div>
      <div class="grid grid-cols-2 sm:grid-cols-3 lg:grid-cols-5 gap-4">
          <div v-for="image in images" :key="image.slug" class="bg-gray-300 h-40">
            <img class="w-full h-full object-cover" :src="image.url" :alt="image.alt" />
          </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  props: ['images']
}
</script>