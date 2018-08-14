<template>
  <main class="container">

    <h1>Hola, soy Francisco Cano Brusa; diseñador y desarrollador web <em class="nowrap">front-end</em> & <em class="nowrap">back-end</em>.</h1>

    <img src="/img/isometric-city.png">

    <p><b>Bienvenido.</b></p>

    <p>Soy desarrollador web especializado en el <em>front-end</em>, y diseñador gráfico.</p>

    <p>En este sitio expongo mi trabajo (<router-link to="/portfolio/">portfolio</router-link>) y reflexiono sobre el diseño de UX, Accesibilidad y otras áreas (<router-link to="/blog/">blog</router-link>). También puedes encontrar <router-link to="/blog/tutoriales/">tutoriales</router-link>.</p>

    <p><b>También me puedes encontrar en...</b></p>

    <icons></icons>
    
    <p>O puedes escribir a <a href="mailto:francanobr@outlook.es">francanobr@outlook.es</a>.</p>

    <hr>

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

let jsonLd = {
    "@context": "http://schema.org",
    "@type": "Person",
    "name": "Francisco Cano Brusa",
    "url": "https://www.francisco-cano.com",
    "jobTitle": "Front-end developer",
    "alumniOf": "Universidad Provincial de Córdoba",
    "gender": "male",
    "sameAs": [
        "https://github.com/aeonfr",
        "https://instagram.com/franciscocanobrusa",
        "https://www.linkedin.com/in/francisco-cano-brusa/",
        "https://codepen.io/frankno/"
    ]
};

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
    title: 'Mi sitio web personal',
    meta: [
      { hid: 'og:url', name: 'og:url', content: 'https://www.francisco-cano.com/' },
    ],
    __dangerouslyDisableSanitizers: ['script'],
    script: [
      {
        hid: "netlifyIdentity",
        type: "text/javascript",
        src: "https://identity.netlify.com/v1/netlify-identity-widget.js"
      },
      {
        hid: 'jsonLd',
        innerHTML: JSON.stringify(jsonLd),
        type: 'application/ld+json',
      }
    ]
  }
};
</script>

