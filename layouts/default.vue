<template>
  <div>
    <header class="serif bg-light-gray pa3 flex items-center fixed w-100 top-0 shadow-2 z-999 sans-serif">
    
      <section class="mr3-ns mr4-l">
        <nuxt-link to="/" class="f4 f3-ns b lh-copy link black-80">
          Francisco Cano Brusa
        </nuxt-link>
      </section>
      <nav role="navigation" class="ml-auto flex-grow-1 measure" ref="menu">
        <div  class="ml-auto flex-grow-1 tr dn-l top-2">
          <a href="#menuAriaReference" class="i-menu f3 black-80 ph2" tabindex="0"
            aria-role="button" :aria-expanded="(isMenuOpen) ? 'true' : 'false'"
            aria-controls="menuAriaReference"
            @keypress.enter="setMenuState('open')" @click.prevent="setMenuState('open')">
            <span class="o-0 f6 absolute">Menu</span>
          </a>
        </div>
        <ul id="menuAriaReference" class="list pa0 mt3 mb0 ma0-l flex-l static-l f5-l tc-l pa0"
          :class="{
            'active bg-light-gray f3 shadow-2': isMenuOpen,
            'dn': !isMenuOpen, 'anim-disappear-from-left': isMenuClosing }">
          <li class="dn-l black-60 small-caps" aria-role="button" aria-label="Cerrar" tabindex="0"
              @keypress.enter="setMenuState('start-closing')" @click="setMenuState('start-closing')">
            <a class="link gray" href="#" @click.prevent>
              <i class="dn-l i-close"></i>
              Menú
            </a>
          </li>
          <li class="w-33-l"><nuxt-link class="link black-80 db hover-blue" to="/">Inicio</nuxt-link></li>
          <li class="w-33-l"><nuxt-link class="link black-80 db hover-blue" to="/portfolio/">Portfolio</nuxt-link></li>
          <li class="w-33-l"><nuxt-link class="link black-80 db hover-blue" to="/blog/">Blog</nuxt-link></li>
        </ul>
      </nav>

    </header>
    <div style="height: 4.25rem"></div>
    
    <!-- Main Content -->
    <main>
      <nuxt/>
    </main>

    <footer class="container bg-light-gray pv3">
      <h1 class="f5">Mapa del sitio</h1>

      <ul class="sans-serif">
        <li><router-link class="link blue" to="/">Inicio</router-link></li>
        <li><router-link class="link blue" to="/portfolio">Portfolio</router-link></li>
        <li><router-link class="link blue" to="/blog">Blog</router-link></li>
      </ul>

      <h1 class="f5">Sobre este sitio</h1>


      <p class="f6">Codificado en Barcelona, España, el 6 de Junio de 2018.
        <br>Todos los derechos reservados.</p>
      <p class="f6">El código fuente se puede consultar <a href="//github.com/aeonfr/francisco-cano.com">aquí</a>.</p>


    </footer>
  </div>
</template>

<script>
export default{
  data(){
    return {
      menuState: 'start-close',
      isMenuClosing: 0,
    }
  },
  methods: {
    setMenuState (newState) {
      if (newState == 'start-closing'){
        this.isMenuClosing = 1;
        let vm = this;
        window.setTimeout(function(){
          vm.isMenuClosing = 0;
          vm.setMenuState('closed');
        }, 250);
      } else this.menuState = newState;

      // Close the menu when clicking outside of the menu
      if (newState == 'open'){
        window.addEventListener('click', this.closeMenuWhenClickingOutsideOfMenu)
      } else {
        window.removeEventListener('click', this.closeMenuWhenClickingOutsideOfMenu)
      }
    },
    closeMenuWhenClickingOutsideOfMenu(ev){
      if (!this.$refs.menu.contains(ev.target))
        this.setMenuState('start-closing');
    }
  },
  computed: {
    isMenuOpen () {
      return (this.menuState == 'open' || this.menuState == 'start-closing');
    }
  }
}
</script>

<style lang="scss">
  li:not(:nth-child(2)) .nuxt-link-active,
  .nuxt-link-exact-active{
    font-weight: 600;
  }
  .sticky{
    position: sticky;
  }
  .container{
    max-width: 44rem;
    margin-left: auto;
    margin-right: auto;
    margin-top: 2rem;
    padding-left: 2rem;
    padding-right: 2rem;
  }
  .i-menu, .i-close{
    display: inline-block;
    width: 1em;
    height: 1em;
  }
  .i-menu::before{
    content: '';
    display: block;
    height: 0.1em;
    width: 0.8em;
    background-color: currentColor;
    margin-top: 0.25em;
    margin-left: 0.1em;
    box-shadow:
      0 0.2em currentColor,
      0 0.4em currentColor;
  }
  .i-close::after, .i-close::before{
    content: '';
    display: block;
    position: absolute;
    height: 0.1em;
    width: 0.8em;
    background-color: currentColor;
    transform: rotate(45deg);
    margin-top: 0.6em;
    margin-left: 0.1em;
  }
  .i-close::after{
    transform: rotate(135deg)
  }


  #menuAriaReference:target, #menuAriaReference.active{
    display: block!important;
    position: fixed;
    top: 0;
    right: 0;
    max-width: 100%;
    line-height: 1.5;
    z-index: 999;
    padding: 0 1em;
    padding-bottom: .5em;
    background: white;
    font-size: 1.5em;
    @extend .anim-appear-from-left;
  }

  @media (min-width: 30em){
    #menuAriaReference:target, #menuAriaReference.active{
      background: transparent;
      position: static;
      font-size: 1em;
      padding-bottom: 0;
      display: flex!important;
      box-shadow: none!important;
    }
  }

  .anim-appear-from-left{
    will-change: transform;
    animation: appear-from-left .25s ease-in-out;
  }
  .anim-disappear-from-left{
    will-change: transform;
    animation: disappear-from-left .25s ease-in-out;
    animation-direction: forwards;
  }
  @keyframes appear-from-left{
    from{ transform: translateX(100%) }
    to{ transform: translateX(0%) }
  }
  @keyframes disappear-from-left{
    to{ transform: translateX(100%) }
  }
</style>