<template>
  <main id="portfolio" class="container">
    <h1>Portfolio</h1>

    <li>
      Aplicación web de gestión de clientes y envío de emails para un pequeño negocio. La App, 100% responsive, fue escrita en Vue.js con back-end en WordPress. <router-link to="/portfolio/storekey" class="nowrap">más información</router-link>
    </li>

    <negate-container>
      <img src="~/assets/portfolio/storekey.jpg">
    </negate-container>

    <router-link to="/portfolio/storekey" class="dib ph3 pv1 bg-blue br-pill mb6 white small-caps link f3" style="margin-top:-3rem">más información</router-link>



    <li>
      Logotipo, identidad corporativa y sitio web para bicicletería, con 3K visitas mensuales en menos de seis meses desde su lanzamiento. <router-link to="/portfolio/bertolinabikes" class="nowrap">más información</router-link>
    </li>
    
    <negate-container>
      <img src="~/assets/portfolio/bertolina-mockup-2.jpg">
    </negate-container>

    <router-link to="/portfolio/bertolinabikes" class="dib ph3 pv1 bg-blue br-pill mt2 mb6 white small-caps link f3">más información</router-link>

    <li>Sitio web para consultora de arquitectura sustentable, desarrollado inicialmente como tema de WordPress ("desde cero"). <a href="https://guiasarq.netlify.com/" target="_blank">Visitar el sitio</a></li>

    <negate-container class="mb6">
      <img src="~/assets/portfolio/guiasarq-mockup.jpg">
    </negate-container>

    <li>Temas para <a href="//blockity.co" target="_blank">blockity</a>, aplicación web para la creación de sitios web.</li>

    <negate-container class="mb6">
      <img src="~/assets/portfolio/blockity-templates.jpg">
    </negate-container>

    <h2 class="mt4">Otros trabajos de diseño gráfico e ilustración</h2>
    <p class="f6">Estos trabajos fueron realizados <em>ad-honorem</em> durante mi cursado en la universidad.</p>

    <div class="mt4"></div>

    <li>Tapa de libro, ilustración xilográfica en blanco y negro, posteriormente coloreada de forma digital.</li>

    <img src="~/assets/portfolio/tapa-libro-redhondinho.jpg">

    <li>Ilustración digital.<br><small>Bob Dylan en dos etapas distintas de su carrera, representado a través de sus frases.</small></li>

    <img src="~/assets/portfolio/dos-ilustraciones.jpg">

    <li>Flyer para Juice Bar (Córdoba).</li>
    
    <img src="~/assets/portfolio/folleto-juice-bar.png">

    <li>Menú de bar, con ilustraciones.</li>

    <img src="~/assets/portfolio/juice-bar.jpg">



    <h2 class="mt4">Más...</h2>
    <p>...en Instagram, CodePen y GitHub.</p>

    <icons></icons>

    <p><router-link to="/" class="f4 link blue">Volver al inicio</router-link></p>

  </main>
</template>

<script>


import Icons from '../../components/icons.vue';
import NegateContainer from '../../components/negateContainer.vue';

  export default {
    name: 'portfolio',
    components: { Icons, NegateContainer },
    head: {
      title: 'Portfolio'
    }
  }

</script>

<style type="text/css">
  #portfolio img{ display: block; margin: 1rem auto; }
  a[target="_blank"]:after {
    content: url(data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAoAAAAKCAYAAACNMs+9AAAAQElEQVR42qXKwQkAIAxDUUdxtO6/RBQkQZvSi8I/pL4BoGw/XPkh4XigPmsUgh0626AjRsgxHTkUThsG2T/sIlzdTsp52kSS1wAAAABJRU5ErkJggg==);
    margin: 0 3px 0 5px;
  }
</style>