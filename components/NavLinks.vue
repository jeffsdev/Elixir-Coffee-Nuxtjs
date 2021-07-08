<template>
    <div class="nav-links">
        <NuxtLink to="/about">About Us</NuxtLink>
        <NuxtLink to="/locations">Locations</NuxtLink>
        <NuxtLink to="/menu">Menu</NuxtLink>
        <a href="#blogposts">Blog</a>
        <a href="#contact">Contact</a>
    </div>
</template>

<script>
export default {
    methods: {
        // linkClicked() {
        //     this.$emit('nav-link-clicked', true);
        // }
    }
}
</script>

<style lang="scss">

</style>