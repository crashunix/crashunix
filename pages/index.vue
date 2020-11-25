<template>
  <div>
    <Cover />
    <Projects :projects="projects"/>
    <About />
    <Blog :articles="articles" />
    <Gallery />
  </div>
</template>

<script>
export default {
  async asyncData({ $content, params }) {
    const projects = await $content("projects", params.slug).fetch();
    const articles = await $content("articles", params.slug).limit(3).fetch();
    return { projects, articles };
  },
};
</script>

<style>
</style>
