<template>
  <main class="page-content-container">
    <HeroVideo />
      <!-- About Section -->
      <section class="page-section section-about">
        <div class="section-inner about-content section--2-col">
          <div class="about-us">
            <h2>About</h2>
            <p>Cappuccino mazagran seasonal pumpkin spice body variety doppio café au lait viennese single origin. Saucer, froth crema, eu plunger pot strong roast robust. Plunger pot, bar id instant café au lait sugar crema.</p>
            <p>Caramelization, foam eu sit coffee flavour cup single shot. Robusta, that, barista rich coffee mazagran that aroma qui single origin. Sweet ut coffee, mocha cup, sit americano and fair trade blue mountain.</p>
            <h3>- Real. Good. Stuff. -</h3>
          </div>
          <img src="~/assets/images/coffeeshop5.jpg" class="img-full" alt="coffee shop">
        </div>
      </section>

      <!-- Location Section  -->
      <section class="page-section section-locations">
        <div class="section-inner locations-content">
          <div class="locations-summary">
            <h2>Locations</h2>
            <p>Single origin, siphon french press, grounds flavour rich java cup wings decaffeinated plunger pot frappuccino. French press, siphon, frappuccino viennese, that steamed sugar java brewed. Shop macchiato.</p>
            <div class="locations-img">
              <img src="~/assets/images/coffeeshop2.jpg" alt="coffee shop">
              <img src="~/assets/images/coffeeshop3.jpg" alt="coffee shop">
            </div>
          </div>
          <div class="locations-addresses">
            <location-item v-for="location in locations" :key="location.name" :location="location" />
          </div>
        </div>
      </section>

      <!-- Location Section  -->
      <section class="page-section section-testimonial">
        <div class="section-inner testimonial-content">
            <span class="openquote">"</span>
            <h4 class="quote">French press, sugar rich cappuccino rich, con panna, cup aromatic extra seasonal cultivar. Aroma, single shot kopi-luwak mug, caffeine wings, fair trade brewed!
              <br>
              <span class="quotesource">&mdash; Han Solo</span>
            </h4>
            <span class="closequote">"</span>
          </div>
      </section>
  </main>
</template>

<script>
export default {
  data() {
    return {
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
      ]
    }
  }
}
</script>

<style lang="scss">


</style>
