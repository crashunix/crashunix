<template>
  <div>
    <header>
      <div class="container mx-auto h-16 lg:h-32 flex justify-center lg:justify-between items-center">
        <h2 v-if="type == 'detail'" class="text-2xl transition duration-500 ease-in-out text-black dark:text-white">{{$nuxt.$route.name | capitalize}}</h2>
        <h2 v-else class="text-2xl duration-500 ease-in-out text-black dark:text-white">crashunix</h2>
        <nav class="hidden lg:flex space-x-6 duration-500 ease-in-out text-black dark:text-white">
          <nuxt-link to="/">Home</nuxt-link>
          <nuxt-link to="/">Projetos</nuxt-link>
          <nuxt-link to="/">Sobre</nuxt-link>
          <nuxt-link to="/">Blog</nuxt-link>
          <nuxt-link to="/">Galeria</nuxt-link>
          <nuxt-link to="/">Contato</nuxt-link>
        </nav>
      </div>
    </header>
  </div>
</template>

<style>
</style>
<script>
export default {
  props: ['type'],
  filters: {
    capitalize(str) {
      const regex = /[a-z]+/ig
      const match = regex.exec(str);
      return match[0].charAt(0).toUpperCase() + match[0].slice(1);
    }
  }
}
</script>
