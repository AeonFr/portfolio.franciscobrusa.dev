<template>
  <main class="container" v-once>
    <article>
      <h1>Proyecto: Bertolina Bikes</h1>

      <p
        class="f4"
      >Diseño de identidad corporativa y desarrollo de sitio web responsive para bicicletería.</p>

      <p>Sitio web desarrollado desde cero durante los últimos meses del 2017. En menos de seis meses alcanzó las 3K visitas mensuales y actualmente tiene un promedio de 3.4K mensual.</p>

      <p>El sitio web se genera como un sitio estático y esto permite que el hosting sea gratuito (con Netlify); por otro lado mediante APIs se consultan los precios y actualizan durante el proceso de construcción.</p>

      <p>
        Desarrollado conjuntamente con la identidad corporativa de la empresa (logotipo,
        <a
          href="https://www.bertolinabikes.com.ar/meta/manual-de-identidad/"
          target="_blank"
          rel="nofollow"
        >Manual de Identidad</a>, piezas gráficas). Se trabajó con la metodología del Design Thinking, con un fuerte anclaje en la investigación.
      </p>

      <p>
        El resultado de la primera iteración (investigación - creativo - prototipado - testeo) se redactó en forma de libro y se puede
        <a
          href="/download/2017-12-09-bertolinabikes-A4-2-bklt.pdf"
          target="_blank"
          rel="nofollow"
        >descargar en PDF</a>.
      </p>

      <negate-container>
        <img src="~/assets/portfolio/bertolina-mockup-2.jpg" />
        <div class="flex-ns tc items-start flex-wrap justify-center">
          <img class="w-25-l" src="~/assets/portfolio/logo-animado.gif" />
          <img class="w-75-l" src="~/assets/portfolio/bertolina-mockup.png" />
        </div>
      </negate-container>

      <div class="ph4 pv1 shadow-2">
        <p>
          Desde comienzos del 2019 el sitio web fue migrado a una plataforma de
          <em
            class="nowrap"
          >e-commerce</em> latinoamericana.
        </p>
        <p>
          El autor ya no responde por el sitio ubicado en
          "bertolinabikes.com.ar", por ende se han quitado los links a dicho sitio.
        </p>
        <p>
          Aún así, se ha habilitado
          <a
            href="https://bertolinabikes.netlify.com/"
            target="_blank"
            rel="nofollow"
          >una vista previa del sitio original</a>
          que se puede consultar siguiendo el enlace.
        </p>
      </div>
    </article>

    <p>
      <router-link to="/portfolio" class="f4 link main">Volver al Portfolio</router-link>
    </p>
  </main>
</template>

<script>
import NegateContainer from "../../components/negateContainer.vue";

export default {
  name: "portfolio-bertolinabikes",
  components: { NegateContainer },
  head: {
    title: 'Portfolio: Proyecto "bertolinabikes"'
  }
};
</script>