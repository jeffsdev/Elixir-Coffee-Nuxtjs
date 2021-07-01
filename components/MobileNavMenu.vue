<template>
    <div class="mobile-nav-menu">
        <NavLinks/>
    </div>
</template>

<script>
export default {

}
</script>

<style lang="scss">
.mobile-nav-menu {
    position: fixed;
    display: flex;
    flex-direction: column;
    justify-content: flex-start;
    align-items: flex-start;
    top: 3.5em;
    right: -15em;
    background: $coffee-black;
    width: 15em;
    height: calc(100vh - 3.5em);
    transition: all 0.3s ease-in-out;
    border-left: 2px solid $coffee-dark;
    z-index: 9;
    .nav-links {
        display: flex;
        flex-direction: column;
        width: 100%;
    }    
    a {
        padding: .75em 1.25em;
        height: auto;
        background: lighten($coffee-black, 10%);
        width: 100%;
        text-align: right;
        font-size: 1.125em;
        border-bottom: .125em solid $coffee-black;
        &:hover,
        &:active,
        &:focus {
            color: $coffee-light;
            background: $coffee-dark;
            transition: 0.3s;
        }
    }
    &.active {
        right: 0;
        transition: all 0.3s ease-in-out;
    }
    @media screen and #{$sm-tablet} {   
        display: none;
    }
}

.nav-menu-open .mobile-nav-menu {
    right: 0;
    transition: all 0.3s ease-in-out;
}

</style>
