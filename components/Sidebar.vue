<template>
  <div class="fixed lg:sticky px-6 lg:p-0 h-16 lg:h-full w-full lg:w-16 lg:w-32 border-r flex lg:flex-col justify-between transition-colors duration-500 ease-in-out z-10" :class="{white_sidebar: scrollPosition > 50}">
    <div class="h-16 lg:h-32 flex justify-center items-center">
        <img v-if="type != 'detail'" src="~assets/icons/code.svg" alt="bar-chart-2"/>
        <a v-else @click="$router.go(-1)" class="cursor-pointer">
          <img class="w-6" src="~assets/icons/arrow-left.svg" alt="Back" />
        </a>
    </div>
    <div class="h-16 lg:h-32 flex justify-center items-center">
        <img src="~assets/icons/moon.svg" alt="moon"/>
    </div>
  </div>
</template>
<style>
  .white_sidebar {
    @apply bg-white;
  }
</style>
<script>
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
  },
  mounted() {
    window.addEventListener('scroll', this.updateScroll);
  }
}
</script>