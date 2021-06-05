<template>
    <div class="blogpost">
        <img :src="imgSrcPath(post.image)" :alt="post.title">
        <div class="post-content">
            <h3>{{ post.title }}</h3>
            <span class="blogpost-date">{{ post.date }}</span>
            <p class="blogpost-preview">{{ post.text }}</p>
            <a href="#" class="readmore button--default">Read More</a>
        </div>
    </div>
</template>

<script>
export default {
    props: ['post'],
    methods: {
        imgSrcPath: function(image) {
            return require(`~/assets/images/${image}`);
        }
    }
}
</script>