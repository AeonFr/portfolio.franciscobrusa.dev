<template>
  <div>
    <header class="serif bg-light-gray pa3 fc-serif flex-ns items-center">
    
      <section class="mr3-ns mr4-l">
        <a href="/" class="f3 lh-copy link black-80">
          Francisco Cano
        </a>
      </section>
      <nav class="ml-auto flex-grow-1 measure">
        <ul class="list pa0 mt3 mb0 ma0-ns flex tc">
          <li class="w-50"><nuxt-link class="link black-80 db hover-blue" to="/">Inicio</nuxt-link></li>
          <li class="w-50"><nuxt-link class="link black-80 db hover-blue" to="/portfolio/">Portfolio</nuxt-link></li>
        </ul>
      </nav>

    </header>
    <nuxt/>
    <footer class="container">
      <h1 class="f5">Mapa del sitio</h1>

      <ul>
        <li><router-link to="/">Inicio</router-link></li>
        <li><router-link to="/blog">Blog</router-link></li>
        <li><router-link to="/portfolio">Portfolio</router-link></li>
      </ul>

      <h1 class="f5">Sobre este sitio web</h1>


      <p class="f6">Este sitio web fue codificado en Barcelona, España, el 6 de Junio de 2018.
        <br>Todos los derechos reservados.</p>

      <p class="f6">Agradecimientos: <a href="//netlify.com">Netlify</a> por el hosting gratuito y todo lo demás (netlify cms = ♥). <a href="https://nuxtjs.org/">Nuxt.j</a> y <a href="https://tachyons.io/">Tachyons.css</a> porque me ofrecieron una grata experiencia para desarrollar este sitio.</p>


      <p class="f6">El código fuente de este sitio se puede consultar <a href="//github.com/aeonfr/francisco-cano.com">aquí</a>.</p>


    </footer>
  </div>
</template>

<style>
  .container{
    max-width: 44rem;
    margin-left: auto;
    margin-right: auto;
    margin-top: 2rem;
    padding-left: 2rem;
    padding-right: 2rem;
  }
</style>