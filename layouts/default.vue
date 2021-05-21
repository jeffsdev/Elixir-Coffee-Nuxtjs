<template>
  <div class="page-wrapper" :class="{ 'nav-menu-open': mobileNavOpen }">
    <Header v-on:nav-menu-open="mobileNavOpen = !mobileNavOpen" v-on:window-resized="mobileNavOpen = false" />
    <MobileNavMenu />
    <Nuxt />
  </div>
</template>

<script>
export default {
  data() {
    return {
      mobileNavOpen: false
    }
  }
}
</script>

<style lang="scss">
body {
  background: $light-tan;
  overflow-x: hidden;
}
.page-wrapper {
  // darken the rest of the page when mobile nav is open
  &::after {
    content: '';
    display: block;
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    min-height: 0;
    height: 0;
    background: #000;
    opacity: 0;
    z-index: 5;
    transition: .3s;
    pointer-events: none;
    @media screen and #{$desktop} {
      display: none !important;
    }
  }
  &.nav-menu-open::after {
      min-height: 1000px;
      height: 100%;
      transition: .3s;     
      pointer-events: initial; 
      opacity: 0.75;
  }
}

</style>
