<template>
  <div class="pt-10 pb-20">
    <div class="container mx-auto space-y-10">
      <div class="flex justify-between">
        <span>Projetos</span>
        <nuxt-link class="flex items-center space-x-2" to="/projects"><span>Todos</span><img class="w-5" src="~assets/icons/arrow-right.svg" alt="todos" /></nuxt-link>
      </div>
      <div class="grid grid-cols-1 lg:grid-cols-5 gap-4">
          <div v-for="project in projects" :key="project.slug" class="h-64 bg-gray-300" :class="`lg:row-span-${project.rowSpan} lg:col-span-${project.colSpan}`"></div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  props: ['projects']
}
</script>