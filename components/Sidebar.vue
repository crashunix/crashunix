<template>
  <div class="fixed lg:sticky px-6 lg:p-0 h-16 lg:h-full w-full lg:w-16 lg:w-32 border-r flex lg:flex-col justify-between transition-colors duration-500 ease-in-out z-10 dark:bg-blue-200" :class="{white_sidebar: scrollPosition > 50}">
    <div class="h-16 lg:h-32 flex justify-center items-center">
        <object v-if="type != 'detail'" data="https://www.flaticon.com/svg/static/icons/svg/1829/1829070.svg" type="image/svg+xml">
          CODE
        </object>
        <a v-else @click="$router.go(-1)" class="cursor-pointer">
          <img class="w-6" src="~assets/icons/arrow-left.svg" alt="Back" />
        </a>
    </div>
    <button @click="toggleTheme('dark-theme')" class="h-16 lg:h-32 flex justify-center items-center">
      {{theme}}
        <img v-if="theme == 'light-theme'" src="~assets/icons/moon.svg" alt="moon"/>
        <img v-else src="~assets/icons/sun.svg" alt="sun"/>
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