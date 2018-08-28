<template>

  <negate-container class="flex-ns items-start ph2 pl5-ns" v-once>
      
      <div>
        <h1>Aplicación Web de gestión de clientes</h1>
        <p>Contabilidad, gestión de clientes y envío de notificaciones, todo desde esta App creada a medida.</p>
        <template v-if="$route.path.startsWith('/portfolio')">
            <router-link to="/portfolio/storekey" :class="btnClass">
              Más información
            </router-link>
        </template>
        <template v-else>
          <a href="https://storekey-demo.francisco-cano.com/app" target="_blank" rel="nofollow"
            :class="btnClass" class="f4">
            Demo
          </a>
        </template>
      </div>
      <img src="~/assets/portfolio/storekey.jpg">
    </negate-container>

</template>
<script>

  import NegateContainer from '~/components/negateContainer.vue';


  export default {
    name: 'storekey-jumbotron',
    components: { NegateContainer },
    data(){
      return{
        btnClass: 'dib link bg-blue br-pill pv2 ph3 white'
      }
    }
  }
</script>