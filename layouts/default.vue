<template>
  <div class="lg:h-screen lg:flex" :class="theme">
    <Sidebar />
    <div class="flex-1 h-full overflow-y-auto px-8">
      <Header />
      <Nuxt />
    </div>
  </div>
</template>

<style>
</style>

<script>
import { mapGetters } from 'vuex';
export default {
  data() {
    return {};
  },
  computed: {
    ...mapGetters('theme', ['getTheme']),
    theme() {
      return this.getTheme;
    }
  }
};
</script>
