<template>
  <main class="container">
    <h2>Blog</h2>
    <section v-if="posts.length">
      
      <ul class="list pa0">
        <li v-for="post in posts" :key="post.date">
          <nuxt-link :to="post._path"
                     class="flex-ns link mv2 pv2 hover-bg-light-gray dark-blue hover-navy">
            <div class="w-100 flex-grow-1" style="order: 2">
              {{ post.title }}
            </div>
            <div class="w4-ns tc gray" style="order: 1">
              {{ prettyDate(post.date) }}
            </div>
          </nuxt-link>
        </li>
      </ul>
    </section>
    <div v-else>
      Aún no hay publicaciones en el blog.
    </div>

    <newsletter></newsletter>
  </main>
</template>

<script>

import Newsletter from '../../components/newsletter.vue';

import { orderBy } from 'lodash';

export default {
  components: { Newsletter },
  data() {
    // Using webpacks context to gather all files from a folder
    const context = require.context('~/content/blog/posts/', false, /\.json$/);

    const posts = context.keys().map(key => ({
      ...context(key),
      _path: `/blog/${key.replace('.json', '').replace('./', '')}`
    }));

    

    return { posts: orderBy(posts, 'date').reverse() };
  },
  head: {
    title: 'Blog'
  },
  methods: {
    prettyDate(d){
      var date = new Date(d);
      return date.getDate() + '/' + (date.getMonth()+1) + '/' + date.getFullYear()
    }
  },
  transition: {
    css: false,
    beforeLeave(el){
      if (this.$route.path == '/blog/') return;
      el.classList.add('slide-right-out');
    },
    leave(el, done){
      if (this.$route.path == '/blog/') return done();
      el.classList.add('slide-right-out');
      window.setTimeout(function(){
        done();
      }, 250)
    }
  }
};
</script>

<style>
.slide-right-out{
  transform: translateX(0);
  opacity: 1;
  animation: slide-right .25s ease-in;
  animation-direction: forwards;
}

@keyframes slide-right{
  from{ opacity: 1; transform: translateX(0) }
  to{ opacity: 0; transform: translateX(-5rem) }
}
</style>