<template>
  <main class="container">
    <storekey-jumbotron />

    <ul class="list pa0 f4 mt5">
      <li>100% Responsive</li>
      <li>
        <em>Front-end</em> en Vue.js
      </li>
      <li>
        <em>Back-end</em> en vanilla PHP y funciones de WordPress
      </li>
    </ul>

    <p class="lh-copy">
      Permitió automatizar tareas como imprimir fichas de cliente,
      ahorrando tiempo y dinero al generar emails de forma masiva
      y evitar envió de cartas por correo (tradicional).
    </p>

    <p class="lh-copy mb4">
      <a
        href="https://storekey-demo.francisco-cano.com/app"
        target="_blank"
        rel="nofollow"
        class="link main"
      >
        <b>Click para acceder al demo</b>
      </a>
      <br />
      <span
        class="f6 inverted-60"
      >Nota: Algunas funciones, como la generación de PDFs, no están disponibles en la demo.</span>
    </p>

    <p>
      <router-link to="/portfolio" class="f4 link main">Volver al Portfolio</router-link>
    </p>
  </main>
</template>

<script>
import StorekeyJumbotron from "~/components/portfolio/storekey.vue";

export default {
  name: "portfolio-storekey",
  components: { StorekeyJumbotron },
  head: {
    title: 'Portfolio: Proyecto "storekey"'
  }
};
</script>