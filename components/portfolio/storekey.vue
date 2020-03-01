<template>
  <negate-container class="flex-ns items-start ph4 pl4-ns" v-once>
    <div>
      <h1>Aplicación Web de gestión de clientes</h1>
      <p>Contabilidad, gestión de clientes y envío de notificaciones por e-mail.</p>
      <template v-if="more">
        <router-link to="/portfolio/storekey" :class="btnClass">Más información</router-link>
      </template>
      <a
        href="https://storekey-demo.francisco-cano.com/app"
        target="_blank"
        rel="nofollow"
        :class="btnClass"
        class="mt2"
      >Demo</a>
    </div>
    <img src="~/assets/portfolio/storekey.jpg" class="pl4" />
  </negate-container>
</template>
<script>
import NegateContainer from "~/components/negateContainer.vue";

export default {
  name: "storekey-jumbotron",
  props: {
    more: Boolean // Si se muestra (O NO) el botón de "Más información"
  },
  components: { NegateContainer },
  data() {
    return {
      btnClass: "dib link br-pill pv1 ph2 bg-inverted-10 inverted-100"
    };
  }
};
</script>