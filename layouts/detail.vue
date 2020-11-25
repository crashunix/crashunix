<template>
  <div class="lg:h-screen lg:flex">
    <Sidebar type="detail" />
    <div class="flex-1 h-full overflow-y-auto px-8">
      <Header />
      <Nuxt />
    </div>
  </div>
</template>

<style>
</style>

<script>
export default {
  data() {
    return {};
  },
};
</script>
