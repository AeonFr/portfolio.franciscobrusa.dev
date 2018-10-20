<template>
  <main class="container">
    <h2>Blog</h2>
    <blog-list/>

    <!-- To do: GDPR newsletter -->
  </main>
</template>

<script>

import Newsletter from '~/components/newsletter.vue';

import BlogList from '~/components/blog/list.vue';


export default {
  components: { Newsletter, BlogList },
  head: {
    title: 'Blog'
  },
  
};
</script>
