<template>
  <main class="container">

    <section class="lh-copy">

      <p><b>Bienvenido.</b></p>

      <p>Soy desarrollador web apasionado por la usabilidad y la experiencia de usuario.</p>

      <p>
        En este sitio expongo mi trabajo (<router-link to="/portfolio/">portfolio</router-link>)
        y reflexiono sobre el diseño de UX, Accesibilidad y otras áreas
        (<router-link to="/blog/">blog</router-link>).
      </p>
    
    </section>

    <p><b>También me puedes encontrar en...</b></p>

    <icons></icons>
    
    <p>O puedes escribir a <a href="mailto:francanobr@outlook.es">francanobr@outlook.es</a>.</p>

    <hr>

    <section>
      
      <h2>Blog</h2>
      <blog-list />

    </section>

  </main>
</template>

<script>

import Icons from '~/components/icons.vue';
import Newsletter from '~/components/newsletter.vue';
import BlogList from '~/components/blog/list.vue';


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
  components: { Icons, Newsletter, BlogList },
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

