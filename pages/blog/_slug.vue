<template>
  <div>

    <article class="container">
      <h1>{{ post.title }}</h1>
      <vue-markdown class="lh-copy" :watches="[]" :breaks="false" :emoji="false" :linkify="false" :anchorAttributes="{ 'target': '_blank' }" :source="post.body">
      </vue-markdown>
    </article>
  </div>
</template>

<script>

import VueMarkdown from 'vue-markdown';


export default {

  components: { VueMarkdown },
  
  async asyncData({ params }) {
    let post = await import('~/content/blog/posts/' + params.slug + '.json');
    return {
      post,

    };
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
    let title = this.post.title,
    excerpt = this.post.body.substring(0, 150) + '...',
    jsonLd = {
        "@context": "http://schema.org",
        "@type": "BlogPosting",
        "headline": title,
        "url": this.url,
        "datePublished": this.post.date,
        "image": {
          "@type": "ImageObject",
          "url": "https://www.francisco-cano.com/img/isometric-city.png",
          "height": 1000,
          "width": 1000
        },
        "author": {
            "@type": "Person",
            "name": "Francisco Cano Brusa",
            "url": "https://www.francisco-cano.com"
        },
        "publisher": {
            "@type": "Organization",
            "name": "Franccisco Cano Brusa",
            "url": "https://www.francisco-cano.com",
            "logo": {
              "@type": "ImageObject",
              "url": "https://www.francisco-cano.com/img/logo.png",
              "height": 700,
              "width": 700
            }
        }
    };
    return {
      title,
      meta: [
        { hid: 'og:type', name: 'og:type', content: 'article' },
        { hid: 'og:description', name: 'og:description', content: excerpt },
      ],
      __dangerouslyDisableSanitizers: ['script'],
      script: [
        {
          hid: 'jsonLd',
          innerHTML: JSON.stringify(jsonLd),
          type: 'application/ld+json',
        }
      ]
    }
  },
};
</script>