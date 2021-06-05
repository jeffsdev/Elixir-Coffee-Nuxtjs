<template>
    <nav class="navbar" :class="{ 'active': open }">
        <NavLinks />
    </nav>
</template>

<script>
export default {
    props: ['open'],
    data() {
        return {
            mobileNav: true
        }
    },
    created() {

    }
}
</script>

<style lang="scss">
.navbar {
    display: none;
    @media screen and #{$sm-tablet} {        
        display: flex;
        position: static;
        flex-direction: row;
        align-items: center;     
        justify-content: center;
        height: 100%;
        width: auto;
        border: none;
        .nav-links {
            display: flex;
            flex-direction: row;
            width: auto;
            height: 100%;
        }        
        a {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            font-size: 1em;
            font-family: $slabstack;
            color: $coffee-light;
            padding: 0 1.25em;
            height: 100%;
            border: none;
            @media screen and #{$desktop} and (min-height: 640px){
                font-size: 1.25em;
            }        
        }
        a:hover {
            background: lighten($coffee-black, 10%);
            color: $light-tan;
        }
        a:active {
            background: lighten($coffee-black, 15%);
        }
    }
}

</style>
