<template>
  <main id="portfolio" class="container">
    <h1>Portfolio</h1>

    <p>Sitio web para <em>Guías: Gestión Integral en Arquitectura Sustentable</em>. <a href="https://guiasarq.netlify.com/" target="_blank">Link</a></p>

    <img src="~/assets/portfolio/guiasarq-mockup.jpg">

    <p>Logotipo e identidad corporativa</p>
    <img src="~/assets/portfolio/bertolina-mockup.png">
    <img src="~/assets/portfolio/logo-animado.gif">

    <p>Sitio web de <em>e-commerce</em> responsivo y optimizado para conecciones lentas. <a href="https://www.bertolinabikes.com.ar/" target="_blank">Link</a></p>

    <img src="~/assets/portfolio/bertolina-mockup.jpg">

    <p>Tapa de libro, ilustración con xilografía en blanco y negro, posteriormente coloreada de forma digital.</p>

    <img src="~/assets/portfolio/tapa-libro-redhondinho.jpg">

    <p>Ilustración digital.<br><small>Bob Dylan en dos etapas distintas de su carrera, representado a través de sus frases.</small></p>

    <img src="~/assets/portfolio/dos-ilustraciones.jpg">

    <p>Afiche para Facultad de Arte y Diseño Lino Enea Spilmbergo.<br><small>Fotografía por <a href="https://deathtothestockphoto.com/" target="_blank">deathtostockphoto</a>.</small></p>

    <img src="~/assets/portfolio/afichespili-mockup.jpg">

    <p>Flyer. (ad-honorem)</p>
    
    <img src="~/assets/portfolio/folleto-juice-bar.png">

    <p>Menú de bar, con ilustraciones. (ad-honorem)</p>

    <img src="~/assets/portfolio/juice-bar.jpg">

    <p>Collage digital.<br><small>Licencia <a href="https://creativecommons.org/licenses/by/2.0/es/" target="_blank">Creative Commons 2.0</a>.</small></p>

    <img src="~/assets/portfolio/collage-creatividad.jpg">

    <p>Temas para <a href="//blockity.co" target="_blank">blockity</a>, aplicación web para la creación de sitios web.</p>

    <img src="~/assets/portfolio/blockity-templates.jpg">

    <p><b>Eso es todo.</b></p>



    <p>También puedes seguirme en Instagram y CodePen para ver creaciones nuevas, o en GitHub para ver el código fuente de algunas de las creaciones de este portfolio (incluido este mismo sitio web).</p>

    <icons></icons>

    <p><router-link to="/" class="f4 link blue">Volver al inicio</router-link></p>

  </main>
</template>

<script>


import Icons from '../components/icons.vue';

  export default {
    name: 'portfolio',
    components: { Icons },
  }

</script>

<style type="text/css">
  #portfolio img{ display: block; margin: 1rem auto; }
</style>