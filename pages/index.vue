<template>
  <main class="container">
    <section>
      <h2>Blog</h2>
      <blog-list />
    </section>

    <hr class="mb5" />

    <section>
      <h2>Social</h2>
      <icons></icons>
    </section>
  </main>
</template>

<script>
import Icons from "~/components/icons.vue";
import BlogList from "~/components/blog/list.vue";

let jsonLd = {
  "@context": "http://schema.org",
  "@type": "Person",
  name: "Francisco Cano Brusa",
  url: "https://www.francisco-cano.com",
  jobTitle: "Front-end developer",
  alumniOf: "Universidad Provincial de Córdoba",
  gender: "male",
  sameAs: [
    "https://github.com/aeonfr",
    "https://instagram.com/franciscocanobrusa",
    "https://www.linkedin.com/in/francisco-cano-brusa/",
    "https://codepen.io/frankno/"
  ]
};

export default {
  components: { Icons, BlogList },
  head: {
    title: "Home",
    meta: [
      {
        hid: "og:url",
        name: "og:url",
        content: "https://www.francisco-cano.com/"
      }
    ],
    __dangerouslyDisableSanitizers: ["script"],
    script: [
      {
        hid: "netlifyIdentity",
        type: "text/javascript",
        src: "https://identity.netlify.com/v1/netlify-identity-widget.js"
      },
      {
        hid: "jsonLd",
        innerHTML: JSON.stringify(jsonLd),
        type: "application/ld+json"
      }
    ]
  }
};
</script>

