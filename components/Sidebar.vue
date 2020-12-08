<template>
  <div class="fixed lg:sticky px-6 lg:p-0 h-16 lg:h-full w-full lg:w-16 lg:w-32 border-r border-gray-200 dark:border-black flex lg:flex-col justify-between transition-colors duration-500 ease-in-out z-10 dark:bg-black" :class="{white_sidebar: scrollPosition > 50}">
    <div class="h-16 lg:h-32 flex justify-center items-center">
        <svg v-if="type != 'detail'" xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="feather feather-code stroke-current text-black dark:text-white transition-colors duration-500 ease-in-out"><polyline points="16 18 22 12 16 6"></polyline><polyline points="8 6 2 12 8 18"></polyline></svg>
        <a v-else @click="$router.go(-1)" class="cursor-pointer">
          <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="feather feather-arrow-left stroke-current text-black dark:text-white transition-colors duration-500 ease-in-out"><line x1="19" y1="12" x2="5" y2="12"></line><polyline points="12 19 5 12 12 5"></polyline></svg>
        </a>
    </div>
    <button @click="toggleTheme('dark-theme')" class="h-16 lg:h-32 flex justify-center items-center">
        <svg v-if="theme !== 'light'" xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="feather feather-moon stroke-current text-black dark:text-white transition-colors duration-500 ease-in-out"><path d="M21 12.79A9 9 0 1 1 11.21 3 7 7 0 0 0 21 12.79z"></path></svg>
        <svg v-else xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="feather feather-sun stroke-current text-black dark:text-white transition-colors duration-500 ease-in-out"><circle cx="12" cy="12" r="5"></circle><line x1="12" y1="1" x2="12" y2="3"></line><line x1="12" y1="21" x2="12" y2="23"></line><line x1="4.22" y1="4.22" x2="5.64" y2="5.64"></line><line x1="18.36" y1="18.36" x2="19.78" y2="19.78"></line><line x1="1" y1="12" x2="3" y2="12"></line><line x1="21" y1="12" x2="23" y2="12"></line><line x1="4.22" y1="19.78" x2="5.64" y2="18.36"></line><line x1="18.36" y1="5.64" x2="19.78" y2="4.22"></line></svg>
    </button>
  </div>
</template>
<style>
  .white_sidebar {
    @apply bg-white;
  }
</style>
<script>

import { mapGetters, mapActions } from "vuex";

export default {
  props: ['type'],
  data() {
    return {
      scrollPosition: null,
    }
  },
  methods: {
    updateScroll() {
      this.scrollPosition = window.scrollY;
    },
    ...mapActions('theme', ['setTheme']),
    toggleTheme() {
      this.setTheme(this.theme == 'light' ? 'dark' : 'light');
    }
  },
  computed: {
    ...mapGetters('theme', ['getTheme']),
    theme() {
      return this.getTheme;
      // return this.$store.getters['theme/getTheme']
    }
  },
  mounted() {
    window.addEventListener('scroll', this.updateScroll);
  }
}
</script>