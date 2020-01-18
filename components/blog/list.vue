<template>
  <div>
    <section v-if="posts.length">
      <ul class="list pa0 sans-serif">
        <li v-for="post in posts" :key="post.date">
          <nuxt-link
            :to="post._path"
            class="db link mv2 pv2 nl1 nr1 ph1 hover-bg-inverted-10 inverted-70"
          >
            <div class="w">{{ post.title }}</div>
            <div class="mt2 f7 inverted-40">{{ prettyDate(post.date) }}</div>
          </nuxt-link>
        </li>
      </ul>
    </section>
    <div v-else>Aún no hay publicaciones en el blog.</div>
  </div>
</template>
<script>
import { orderBy, pullAllBy } from "lodash";

export default {
  name: "blog-list",
  data() {
    // Using webpacks context to gather all files from a folder
    const context = require.context("~/content/blog/posts/", false, /\.json$/);

    const posts = context.keys().map(key => ({
      ...context(key),
      _path: `/blog/${key.replace(".json", "").replace("./", "")}`
    }));

    return {
      posts: orderBy(
        pullAllBy(posts, [{ draft: true }], "draft"),
        "date"
      ).reverse()
    };
  },
  methods: {
    prettyDate(d) {
      var date = new Date(d);
      return (
        date.getDate() + "/" + (date.getMonth() + 1) + "/" + date.getFullYear()
      );
    }
  }
};
</script>