<template>
    <main class="page-content-container blog-page-content">
        <div class="hero-container">
            <h1>Blog</h1>
        </div>
        <section class="page-section">
            <div class="section-inner">
                <div class="latest-posts">
                    <blog-post v-for="post in posts" :key="post.title" :post="post" />
                </div>
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
    }
}
</script>

<style lang="scss" scoped>
    .hero-container {
        background: url('~/assets/images/blog-hero.jpg') center 80%/cover no-repeat;
    }
</style>