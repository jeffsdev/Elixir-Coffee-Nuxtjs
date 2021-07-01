<template>
    <header class="site-header" :class="{ 'header-hidden': !showHeader }">
        <BrandLogo />
        <MainNav :open="navToggled" />
        <NavBurger @click.native="toggleNavMenu" :open="navToggled"/>
    </header>
</template>

<script>
import _ from 'lodash';

export default {
    data() {
        return {
            navToggled: false,
            showHeader: true,
            lastScrollPostion: 0
        }
    },
    watch: {
      $route () {
          this.closeNavMenu();
      }
    },
    methods: {

        toggleNavMenu() {
            if (!this.navToggled) {
                this.navToggled = true;
                this.$emit('nav-menu-open', this.navToggled);
            } else {
                this.navToggled = false;
                this.$emit('nav-menu-closed', this.navToggled);
            }
        },
        closeNavMenu() {
            this.navToggled = false;
            this.$emit('nav-menu-closed', this.navToggled);
        },
        onWindowResize(e) {
            this.navToggled = false;
            this.$emit('window-resized');
        },
        onScroll() {
            const currentScrollPosition = window.pageYOffset || document.documentElement.scrollTop;
            if (currentScrollPosition < 0) {
                return
            }
            if (Math.abs(currentScrollPosition - this.lastScrollPostion) < 60) {
                return
            }
            this.showHeader = currentScrollPosition < this.lastScrollPostion;
            this.lastScrollPostion = currentScrollPosition;
        }
    },
    mounted() {
        window.addEventListener("resize", _.throttle(this.onWindowResize, 1000));
        window.addEventListener("scroll", _.throttle(this.onScroll, 200));
    },
    destroyed() {
        window.removeEventListener("resize", this.onWindowResize);
        window.removeEventListener("scroll", this.onScroll);
    }
}
</script>

<style lang="scss">
.site-header {
    position: fixed;
    display: flex;
    justify-content: space-between;
    background: $coffee-black;
    border-bottom: 0.125em solid $coffee-dark;
    padding: 0 0 0 1em;
    width: 100%;
    max-width: 100vw;
    height: 3.5em;
    transition: .3s;
    z-index: 9;
    transform: translate3d(0,0,0);
    transition: .2s;
    &.header-hidden {
        transform: translate3d(0,-100%,0);
    }
    @media screen and #{$tablet} and (min-height: 640px) {
        height: 4.75em;
    }  
}

.nav-menu-open {
    .site-header.header-hidden {
        transform: none;
    }
}

</style>
