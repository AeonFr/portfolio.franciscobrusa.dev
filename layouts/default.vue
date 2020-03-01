<template>
  <div>
    <header
      class="pa3 flex items-center fixed w-100 top-0 z-999 sans-serif bg-inverted-10"
    >
      <section class="mr3-ns mr4-l">
        <nuxt-link to="/" class="f5 f4-ns b lh-copy link inverted-100"
          >Francisco Brusa</nuxt-link
        >
      </section>
    </header>
    <div style="height: 4.25rem"></div>

    <!-- Main Content -->
    <main>
      <nuxt />
    </main>

    <footer class="container pv3">
      <h1 class="f3">Francisco Brusa</h1>
      <p>
        <em>Barcelona-based front end developer</em>
      </p>
      <nav class="sans-serif">
        <p class="f5">
          <nuxt-link class="link dib pr2 mr2 main" to="/">Portfolio</nuxt-link>
          <a class="link dib pr2 mr2 main" href="https://www.franciscobrusa.dev"
            >Blog</a
          >
        </p>
      </nav>
    </footer>
  </div>
</template>

<style>
li:not(:nth-child(2)) .nuxt-link-active,
.nuxt-link-exact-active {
  font-weight: 600;
}
.sticky {
  position: sticky;
}
.container {
  max-width: 44rem;
  margin-left: auto;
  margin-right: auto;
  margin-top: 2rem;
  padding-left: 2rem;
  padding-right: 2rem;
}
</style>
