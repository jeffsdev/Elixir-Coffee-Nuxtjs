<template>
    <div class="blogpost">
        <img :data-src="require(`~/assets/images/${post.image}`)" class="lozad" :alt="post.title">
        <div class="post-content">
            <h3>{{ post.title }}</h3>
            <span class="blogpost-date">{{ post.date }}</span>
            <p class="blogpost-preview">{{ post.text }}</p>
            <a href="#" class="readmore button--default">Read More</a>
        </div>
    </div>
</template>

<script>
import lozad from 'lozad';

export default {
    props: ['post'],
    methods: {
        imgSrcPath: function(image) {
            return require(`~/assets/images/${image}`);
        }
    },
    mounted() {
        const observer = lozad('.lozad', {
            rootMargin: '100px 0px',
        });
        observer.observe();
    }    
}
</script>