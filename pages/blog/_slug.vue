<template>
  <article class="container">
    <h1>{{ title }}</h1>
    <vue-markdown class="lh-copy" :watches="[]" :breaks="false" :emoji="false" :linkify="false" :anchorAttributes="{ 'target': '_blank' }" :source="body">
    </vue-markdown>
  </article>
</template>

<script>

import VueMarkdown from 'vue-markdown';

export default {

  components: { VueMarkdown },
  
  async asyncData({ params }) {
    // const postPromise = process.BROWSER_BUILD
    //   ? import('~/content/blog/posts/' + params.slug + '.json')
    //   : Promise.resolve(
    //       require('~/content/blog/posts/' + params.slug + '.json')
    //     );
    //     
    //     post: app.$content('posts').get(route.path)

    let post = await import('~/content/blog/posts/' + params.slug + '.json');
    return post;
  },
  data(){
    return {}
  },
  head(){
    var title = this.title,
        excerpt = this.body.substring(0, 150) + '...';
    return {
      title,
      meta: [
        { hid: 'og:type', name: 'og:type', content: 'article' },
        { hid: 'og:description', name: 'og:description', content: excerpt },
      ]
    }
  }
};
</script>
