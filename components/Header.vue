<template>
    <header class="site-header">
        <Logo />
        <Nav :open="navToggled" />
        <NavBurger @click.native="toggleNavMenu" :open="navToggled"/>
    </header>
</template>

<script>
import _ from 'lodash';

export default {
    data() {
        return {
            navToggled: false
        }
    },
    methods: {
        toggleNavMenu() {
            this.navToggled = !this.navToggled;
            this.$emit('nav-menu-open', this.navToggled);
        },
        myEventHandler(e) {
            this.navToggled = false;
            this.$emit('window-resized');
        }
    },
    mounted() {
        window.addEventListener("resize", _.throttle(this.myEventHandler, 1000));
    },
    destroyed() {
        window.removeEventListener("resize", this.myEventHandler);
    },    
}
</script>

<style lang="scss">
.site-header {
    position: relative;
  display: flex;
  justify-content: space-between;
  background: $coffee-black;
  border-bottom: 0.125em solid $coffee-dark;
  padding: 0 0 0 1em;
  height: 3.5em;
  transition: .3s;
  z-index: 9;
  @media screen and #{$tablet} and (min-height: 640px) {
      height: 4.75em;
  }  
}
</style>
