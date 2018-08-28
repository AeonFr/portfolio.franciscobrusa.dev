<template>

  <div>
    <section v-if="posts.length">
      
      <ul class="list pa0 sans-serif">
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
  </div>

</template>
<script>

import { orderBy } from 'lodash';

export default {
  name: 'blog-list',
  data() {
    // Using webpacks context to gather all files from a folder
    const context = require.context('~/content/blog/posts/', false, /\.json$/);

    const posts = context.keys().map(key => ({
      ...context(key),
      _path: `/blog/${key.replace('.json', '').replace('./', '')}`
    }));

    return { posts: orderBy(posts, 'date').reverse() };
  },
  methods: {
    prettyDate(d){
      var date = new Date(d);
      return date.getDate() + '/' + (date.getMonth()+1) + '/' + date.getFullYear()
    }
  },
}
</script>