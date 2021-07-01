<template>
  <div class="page-wrapper" :class="{ 'nav-menu-open noscroll': mobileNavOpen }">
    <SiteHeader 
      v-on:nav-menu-open="mobileNavOpen = true" 
      v-on:nav-menu-closed="mobileNavOpen = false" 
      v-on:window-resized="mobileNavOpen = false" />
    <MobileNavMenu />
    <Nuxt />
    <SiteFooter />
  </div>
</template>

<script>
export default {
  data() {
    return {
      mobileNavOpen: false,
      locations: [
        {
          name: 'Burnside',
          address: '123 E Burnside St',
          hours: '7am - 4pm',
          phone: '(503) 444-4444'
        },
        {
          name: 'Mississippi',
          address: '123 N Mississippi Ave',          
          hours: '7am - 4pm',
          phone: '(503) 555-5555'
        }
      ],
      posts: [
        {
          title: 'Acerbic Percolator',
          date: 'July 12, 2021',
          text: 'Robusta cup steamed barista, affogato, viennese, rich robust white skinny pumpkin spice trifecta organic redeye. Barista eu, single shot organic in grinder instant macchiato. Percolator single shot, in grinder extraction, sit breve est.',
          image: 'blog-img3.jpg'
        },
        {
          title: 'Siphon Crema Espresso',
          date: 'June 12, 2021',
          text: 'Café au lait crema, seasonal foam rich americano rich steamed dripper sit viennese. Decaffeinated, mazagran blue mountain, breve cortado carajillo, rich robust white grounds dripper redeye. Cup spice barista caffeine mug bar.',
          image: 'blog-img2.jpg'
        },
        {
          title: 'Mocha Irish Crema',
          date: 'May 03, 2021',
          text: 'Whipped, extraction roast irish, plunger pot chicory eu shop viennese rich. Milk, aromatic sugar, single origin affogato, café au lait espresso, pumpkin spice mocha aromatic eu cinnamon. Kopi-luwak, single shot latte fair trade single breve.',
          image: 'blog-img1.jpg'
        },                
      ]
    }
  },
  watch: {
      $route () {
          this.mobileNavOpen = false;
      }
  },
}
</script>

<style lang="scss">

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

.noscroll {
    overflow: hidden;
    // max-height: 100vh;
}

</style>
