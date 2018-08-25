<template>
  <main class="container">





    <negate-container class="flex-ns items-start ph2 pl5-ns">
      
      <div>
        <h1>Aplicación Web de gestión de clientes</h1>
        <p>Contabilidad y envío de notificaciones por E-mail y Whatsapp, todo desde esta App creada a medida.</p>
        <a href="https://storekey-demo.francisco-cano.com/app" target="_blank" rel="nofollow"
           class="dib f4 link bg-blue br-pill pv2 ph3 white">
          Demo
        </a>
      </div>
      <img src="~/assets/portfolio/storekey.jpg">
    </negate-container>


    <ul class="list pa0 f4">
      <li>100% Responsive</li>
      <li><em>Front-end</em> en Vue.js</li>
      <li><em>Back-end</em> en vanilla PHP y funciones de WordPress</li>
    </ul>

    <p class="lh-copy">
      Permitió automatizar tareas como imprimir fichas de cliente,
      ahorrando tiempo y dinero al generar emails de forma masiva
      y evitar envió de cartas por correo (tradicional).
    </p>
    <p>
      Actualmente se está re-escribiendo: el front-end será una <abbr>PWA</abbr>
      y el <em>back-end</em> funcionará con el <abbr>ORM</abbr> de Laravel.
      El código se mantiene en
      <a href="https://github.com/AeonFr/storekeyCRM" target="_blank">
        este repositorio de GitHub
      </a>.
    </p>

    <p class="pa2 shadow-2">
      <a href="https://storekey-demo.francisco-cano.com/app" target="_blank" rel="nofollow">Demo</a>
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