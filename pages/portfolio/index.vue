<template>
  <main id="portfolio" class="container" v-once>
    <h1>Portfolio</h1>

    <li class="list mt6">
      <storekey-jumbotron :more="true" />
    </li>

    <li class="mt6 list">
      <timekr />
    </li>

    <li class="mt6 list">
      <h1>E-commerce</h1>

      <ul class="list">
        <li>
          <h2>bertolinabikes</h2>
          <negate-container>
            <div class="mh3 mw7 center">
              <p>Logotipo, identidad corporativa y sitio web para bicicletería.</p>
            </div>
            <div class="tc">
              <router-link
                to="/portfolio/bertolinabikes"
                :class="btnClass"
                class="f4"
              >Más información</router-link>
            </div>
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
          <div class="tc">
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

    <li class="mt6 list">
      <h2 class="mt4">Otros trabajos de diseño gráfico e ilustración</h2>
      <p class="f6 italic">
        Estos trabajos fueron realizados
        <em>ad-honorem</em> durante mi cursado en la universidad.
      </p>
      <ul>
        <li class="mt-4">
          Tapa de libro, ilustración xilográfica en blanco y negro, posteriormente coloreada de forma digital.
          <img
            src="~/assets/portfolio/tapa-libro-redhondinho.jpg"
          />
        </li>
      </ul>
    </li>

    <li>
      Flyer para Juice Bar.
      <img src="~/assets/portfolio/folleto-juice-bar.png" />
    </li>

    <li>
      Menú de bar, con ilustraciones.
      <img src="~/assets/portfolio/juice-bar.jpg" />
    </li>
    <p>
      <router-link to="/" class="f4 link blue">Volver al inicio</router-link>
    </p>
  </main>
</template>

<script>
import Icons from "~/components/icons.vue";
import NegateContainer from "~/components/negateContainer.vue";
import StorekeyJumbotron from "~/components/portfolio/storekey.vue";
import Timekr from "~/pages/portfolio/timekr.vue";

export default {
  name: "portfolio",
  components: { Icons, NegateContainer, StorekeyJumbotron, Timekr },
  head: {
    title: "Portfolio"
  },
  data() {
    return {
      btnClass: "dib link bg-blue br-pill pv2 ph3 white sans-serif tc"
    };
  },
  mounted() {
    document.querySelector("html").style.backgroundColor = "white";
  },
  destroyed() {
    document.querySelector("html").style.backgroundColor = "";
  }
};
</script>

<style type="text/css">
#portfolio img {
  display: block;
  margin: 1rem auto;
}
a[target="_blank"]:after {
  content: url(data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAoAAAAKCAYAAACNMs+9AAAAQElEQVR42qXKwQkAIAxDUUdxtO6/RBQkQZvSi8I/pL4BoGw/XPkh4XigPmsUgh0626AjRsgxHTkUThsG2T/sIlzdTsp52kSS1wAAAABJRU5ErkJggg==);
  margin: 0 3px 0 5px;
}
</style>