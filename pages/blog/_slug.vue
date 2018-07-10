<template>
  <div>

    <article class="container">
      <h1>{{ title }}</h1>
      <vue-markdown class="lh-copy" :watches="[]" :breaks="false" :emoji="false" :linkify="false" :anchorAttributes="{ 'target': '_blank' }" :source="body">
      </vue-markdown>
    </article>
    <section class="container bg-black light-blue pv3">
      
      <h1 class="f3">Compartir</h1>

      <a class="white" :href=" 'https://www.facebook.com/sharer/sharer.php?u=' + url ">Facebook</a>
      -
      <a class="white" :href=" 'https://twitter.com/home?status=' + url ">Twitter</a>
      -
      <a class="white" :href=" 'https://www.linkedin.com/shareArticle?mini=true&url=' + url + '&title=&summary=&source=' + url">LinkedIn</a>
      -
      <a ref="copyButton" aria-role="button" href="#" @click.prevent="copyUrl" @keypress.enter.prevent="copyUrl" class="white">Copiar <abbr>URL</abbr></a>
    </section>
  </div>
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
  computed: {
    url(){
      return encodeURI('https://francisco-cano.com' + this.$route.path);
    },
  },
  methods: {
    copyUrl(){
      var textArea = document.createElement("textarea");
      textArea.value = this.url;
      textArea.setAttribute('class','clip');
      document.body.appendChild(textArea);
      textArea.focus();
      textArea.select();
      try {
        var successful = document.execCommand('copy');
        var msg = successful ? 'successful' : 'unsuccessful';
        console.log('Copying text command was ' + msg);
      } catch (err) {
        console.error('Oops, unable to copy', err);
      }

      document.body.removeChild(textArea);

      // return focus
      this.$refs.copyButton.focus();
    }
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
