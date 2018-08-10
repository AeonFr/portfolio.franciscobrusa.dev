<template>
  <main class="container">
    <h2>Tutoriales</h2>

    <section v-if="posts.length">
      
      <ul>
        <li v-for="post in posts" :key="post.date">
          <nuxt-link :to="post._path">
            {{ post.title }}
          </nuxt-link>
        </li>
      </ul>

    </section>
    <div v-else>
      Aún no hay publicaciones en esta sección.
    </div>
  </main>
</template>

<script>

export default {
  data() {
    // Using webpacks context to gather all files from a folder
    const context = require.context('~/content/blog/tuts/', false, /\.json$/);

    const posts = context.keys().map(key => ({
      ...context(key),
      _path: `/blog/tuts/${key.replace('.json', '').replace('./', '')}`
    }));

    return { posts };
  },
  head: {
    title: 'Tutoriales'
  }
};
</script>

