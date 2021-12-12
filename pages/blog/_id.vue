<template>
  <main class="page-content-container blog-post-content">
    <div class="hero-container" :style="{ backgroundImage: `url(${imgSrcPath(post.image)})` }">
        <h1>{{ post.title }}</h1>
    </div>
    <div class="blog-post__details">
      <strong>Author:</strong> {{ post.author }}
      <br>
      <strong>Date:</strong> {{ post.date }}
    </div>
    <section class="page-section">
        <div class="blog-post__post-content">
          <div v-html="post.body"></div>
          <br>
          <a href="/blog" class="link-hover-underline">&lt; Back to Blog Posts</a>
        </div>
    </section>
  </main>


</template>

<script>
import data from '~/static/data.json';

export default {
    data() {
        return {
            posts: data.posts
        }
    },
    methods: {
      imgSrcPath: function(image) {
          return require(`~/assets/images/${image}`);
      }
    },
    computed: {
      post() {
        return this.posts.find(p => p.id == this.$route.params.id)
      }
    }
}

</script>

<style lang="scss">
  .blog-post-content .hero-container {
    background-size: cover;
    background-position: center;
  }
  .blog-post__details {
    width: 100%;
    background: #fff;
    text-align: center;
    padding: 2em;
    font-size: 1.25em;
  }

  .blog-post__post-content {
    width: 1200px;
    max-width: 100%;
    margin: auto;
  }
</style>