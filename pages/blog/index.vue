<template>
  <main class="container">
    <h2>Blog</h2>
    <blog-list />
  </main>
</template>

<script>
import BlogList from "~/components/blog/list.vue";

export default {
  components: { BlogList },
  head: {
    title: "Blog"
  }
};
</script>
