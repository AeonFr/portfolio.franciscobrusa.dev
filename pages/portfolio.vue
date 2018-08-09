<template>
  <main id="portfolio" class="container">
    <h1>Portfolio</h1>

    <li>Sitio web para <em>Guías: Gestión Integral en Arquitectura Sustentable</em>. <a href="https://guiasarq.netlify.com/" target="_blank">Link</a></li>

    <img src="~/assets/portfolio/guiasarq-mockup.jpg">

    <li>Logotipo e identidad corporativa para <a href="https://www.bertolinabikes.com.ar/" target="_blank">Bertolina Bikes</a></li>
    <img src="~/assets/portfolio/logo-animado.gif">
    <img src="~/assets/portfolio/bertolina-mockup.png">

    <li>Sitio web <em>responsive</em> y optimizado para conecciones lentas. <a href="https://www.bertolinabikes.com.ar/" target="_blank">Link</a>.
    <br>Para el sitio web se creó un sistema de diseño personalizado, documentado en <a href="https://www.bertolinabikes.com.ar/meta/manual-de-identidad/" target="_blank">esta guía de estilo</a>.</li>
    <img src="~/assets/portfolio/bertolina-mockup-2.jpg">

    <li>Temas para <a href="//blockity.co" target="_blank">blockity</a>, aplicación web para la creación de sitios web.</li>

    <img src="~/assets/portfolio/blockity-templates.jpg">

    <h2 class="mt4">Trabajos de diseño gráfico</h2>
    <p class="f6">Estos trabajos fueron realizados <em>ad-honorem</em> durante mi cursado en la universidad.</p>

    <div class="mt4"></div>

    <li>Tapa de libro, ilustración xilográfica en blanco y negro, posteriormente coloreada de forma digital.</li>

    <img src="~/assets/portfolio/tapa-libro-redhondinho.jpg">

    <li>Ilustración digital.<br><small>Bob Dylan en dos etapas distintas de su carrera, representado a través de sus frases.</small></li>

    <img src="~/assets/portfolio/dos-ilustraciones.jpg">

    <li>Afiche para Facultad de Arte y Diseño Lino Enea Spilmbergo.<br><small>Fotografía por <a href="https://deathtothestockphoto.com/" target="_blank">deathtostockphoto</a>.</small></li>

    <img src="~/assets/portfolio/afichespili-mockup.jpg">

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


import Icons from '../components/icons.vue';

  export default {
    name: 'portfolio',
    components: { Icons },
    head: {
      title: 'Portfolio'
    }
  }

</script>

<style type="text/css">
  #portfolio img{ display: block; margin: 1rem auto; }
</style>