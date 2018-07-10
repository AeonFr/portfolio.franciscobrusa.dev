<template>
  <main class="container">

    <h1>Hola, soy Francisco Cano Brusa y soy especialista en el desarrollo web front-end.</h1>

    <img src="/img/isometric-city.png">

    <p><b>Bienvenido.</b></p>

    <p><b>Acerca de mi.</b> Soy desarrollador web especializado en el front-end.</p>

    <p><b>Sobre este sitio.</b> Aquí expongo mi trabajo (<router-link to="/portfolio/">portfolio</router-link>) y reflexiono sobre mi profesión (<router-link to="/blog/">blog</router-link>).</p>

    <p><b>Sígueme en las redes y ponte en contacto!</b> </p>

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
    title: 'Inicio',
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

