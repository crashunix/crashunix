<template>
  <div>
    <Cover />
    <Projects :projects="projects"/>
    <About />
    <Blog :articles="articles" />
    <Gallery :images="images" />
    <Footer />
  </div>
</template>

<script>
export default {
  async asyncData({ $content }) {
    const projects = await $content("projects").fetch();
    const articles = await $content("articles").limit(3).fetch();
    const images = await $content("images").limit(10).fetch();
    return { projects, articles, images };
  },
};
</script>

<style>
</style>
