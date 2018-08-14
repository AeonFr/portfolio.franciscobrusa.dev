<template>
  <main class="container">

    <h1>Proyecto: Storekey</h1>

    <negate-container>
      <img src="~/assets/portfolio/storekey.jpg">
    </negate-container>


    <p class="f4">Creación una aplicación web de gestión de clientes y envío de emails para un pequeño negocio. La App, 100% responsive, fue escrita en Vue.js con back-end en WordPress.</p>

    <p>Permitió automatizar tareas como imprimir fichas de cliente, ahorrando tiempo - pero por otro lado permitió ahorrar dinero al generar emails de forma masiva y evitar envió de cartas por correo (tradicional). 100% responsive; actualmente se está re-escribiendo el <em>back-end</em> con el <abbr>ORM</abbr> de Laravel, con planes de ser lanzado como programa <em>open-source</em> (<a href="https://github.com/AeonFr/storekeyCRM" target="_blank">repositorio de GitHub</a>).</p>

    <p class="pa2 shadow-2">
      <a href="http://storekey-demo.francisco-cano.com/app" target="_blank" rel="nofollow">Demo</a>
      <br> Contraseña: <code>password</code>
      <br><span class="f6 gray">Nota: Algunas funciones, como la generación de PDFs, no están disponibles en la demo.</span>
    </p>

    <p><router-link to="/portfolio" class="f4 link blue">Volver al Portfolio</router-link></p>

  </main>
</template>

<script>

  import NegateContainer from '../../components/negateContainer.vue';


  export default {
    name: 'portfolio-storekey',
    components: { NegateContainer },
    head: {
      title: 'Portfolio: Proyecto "storekey"'
    }
  }

</script>