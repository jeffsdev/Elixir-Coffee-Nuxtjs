<template>
  <main class="page-content-container about-page-content">
    <div class="hero-container">
        <h1>{{ post.title }}</h1>
    </div>
    <section class="page-section">
        <div class="section-inner menu-intro">
          
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
    computed: {
      post() {
        return this.posts.find(p => p.id == this.$route.params.id)
      }
    }
}

</script>