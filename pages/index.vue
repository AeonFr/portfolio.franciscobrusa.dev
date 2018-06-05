<template>
  <main class="container">

    <h1>Hola, soy Francisco Cano y hago diseño y desarrollo web.</h1>

    <img src="/img/isometric-city.png">

    <p><b>Bienvenido a mi sitio web.</b> Soy diseñador gráfico y desarrollador web. Aquí expongo mi trabajo (<router-link to="/portfolio/">portfolio</router-link>) y reflexiono sobre mi profesión (<router-link to="/blog/">blog</router-link>). También puedes encontrarme en estos medios:</p>

    <icons></icons>
    
    <p>O puedes escribir a <a href="mailto:francanobr@outlook.es">francanobr@outlook.es</a>.</p>

    <section v-if="posts.length">
      
      <h2>Blog</h2>
      <ul>
        <li v-for="post in posts" :key="post.date">
          <nuxt-link :to="post._path">
            {{ post.title }}
          </nuxt-link>
        </li>
      </ul>

      <newsletter></newsletter>
    </section>

  </main>
</template>

<script>

import Icons from '../components/icons.vue';
import Newsletter from '../components/newsletter.vue';

export default {
  components: { Icons, Newsletter },
  data() {
    // Using webpacks context to gather all files from a folder
    const context = require.context('~/content/blog/posts/', false, /\.json$/);

    const posts = context.keys().map(key => ({
      ...context(key),
      _path: `/blog/${key.replace('.json', '').replace('./', '')}`
    }));

    return { posts };
  },
  head: {
    title: 'Inicio',
    meta: [
      { hid: 'og:url', name: 'og:url', content: 'https://www.francisco-cano.com/' },
    ]
  }
};
</script>

