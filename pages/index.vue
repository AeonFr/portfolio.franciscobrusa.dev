<template>
  <main id="portfolio" class="container" v-once>
    <h1>Portfolio</h1>

    <li class="list mt6-ns mt4">
      <storekey-jumbotron :more="true" />
    </li>

    <li class="list mt6-ns mt4">
      <timekr />
    </li>

    <li class="list mt6-ns mt4">
      <h1>E-commerce</h1>

      <ul class="list pa0">
        <li>
          <h2>Bertolina Bikes</h2>
          <div class="mw7 center">
            <p>Logotipo, identidad corporativa y sitio web para bicicletería.</p>
          </div>
          <div>
            <router-link to="/portfolio/bertolinabikes" :class="btnClass" class="f4">Más información</router-link>
          </div>
          <negate-container>
            <img
              src="~/assets/portfolio/bertolina-mockup-2.jpg"
              alt="Imágen del sitio web para Bertolina Bikes"
            />
          </negate-container>
        </li>
        <li class="mt6">
          <h2>guiasarq</h2>

          <p>
            Sitio web para consultora de arquitectura sustentable,
            desarrollado inicialmente como tema de WordPress ("desde cero").
          </p>
          <div>
            <a
              href="https://guiasarq.netlify.com/"
              target="_blank"
              :class="btnClass"
              class="f4"
            >Visitar el sitio</a>
          </div>
          <negate-container>
            <img src="~/assets/portfolio/guiasarq-mockup.jpg" />
          </negate-container>
        </li>
      </ul>
    </li>
  </main>
</template>

<script>
import NegateContainer from "~/components/negateContainer.vue";
import StorekeyJumbotron from "~/components/portfolio/storekey.vue";
import Timekr from "~/pages/portfolio/timekr.vue";

export default {
  name: "portfolio",
  components: { NegateContainer, StorekeyJumbotron, Timekr },
  head: {
    title: "Portfolio"
  },
  data() {
    return {
      btnClass: "dib link br-pill pv1 ph2 bg-inverted-10 inverted-100"
    };
  }
};
</script>

<style type="text/css">
#portfolio img {
  display: block;
  margin: 1rem auto;
}
a[target="_blank"]:after {
  content: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 24 24' width='1rem' height='1rem' stroke='white' stroke-width='2' fill='none' stroke-linecap='round' stroke-linejoin='round' class='css-i6dzq1'%3E%3Cpath d='M18 13v6a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V8a2 2 0 0 1 2-2h6'%3E%3C/path%3E%3Cpolyline points='15 3 21 3 21 9'%3E%3C/polyline%3E%3Cline x1='10' y1='14' x2='21' y2='3'%3E%3C/line%3E%3C/svg%3E");
  margin: 0 3px 0 5px;
}
.light-mode a[target="_blank"]:after {
  /* black version */
  content: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 24 24' width='1rem' height='1rem' stroke='black' stroke-width='2' fill='none' stroke-linecap='round' stroke-linejoin='round' class='css-i6dzq1'%3E%3Cpath d='M18 13v6a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V8a2 2 0 0 1 2-2h6'%3E%3C/path%3E%3Cpolyline points='15 3 21 3 21 9'%3E%3C/polyline%3E%3Cline x1='10' y1='14' x2='21' y2='3'%3E%3C/line%3E%3C/svg%3E");
}
</style>