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

      <!-- Our Team Section  -->
      <section class="page-section-full section-team">
        <div class="team-content">
            <h2>Our Team</h2>
            <div class="team-members">
              <div class="team-member" v-for="person in team" :key="person.name" :style="inlineBgImage(person.image)" :aria-label="person.name">
                <span class="team-member-name">{{person.name}}</span>
              </div>
            </div>
          </div>
          <div class="team-message">
            <div class="container">
              <p>Pumpkin spice fair trade froth, viennese turkish java decaffeinated extraction breve aftertaste. Coffee, decaffeinated, medium milk frappuccino brewed whipped. Organic, irish flavour, robust id seasonal aftertaste!</p>
            </div>
          </div>          
      </section>      

      <!-- Recent Blog Posts Section -->
      <section class="page-section section-blogposts">
        <div class="section-inner blogposts-content">
          <h2>Latest Posts</h2>
          <p>In barista medium organic black cultivar rich. Crema at ristretto a and that coffee chicory. Body id single origin strong espresso wings black body. Cup americano caramelization plunger pot robusta milk cortado con panna at ristretto.</p>

          <div class="latest-posts">
            <blog-post v-for="post in posts" :key="post.title" :post="post" />
          </div>

          <a class="moreposts link-hover-underline" href="">View More Blogposts</a>
        </div>
      </section>

      <!-- Gallery Section -->
      <section class="page-section-full section-gallery">
        <div class="section-gallery__header">
          <h3>Steamed dark café au lait aromatic aroma carajillo espresso roast.</h3>
        </div>
        <div class="section-gallery__slider-wrapper">
          <div class='section-gallery__slider'>
            <div v-for="image in galleryImages" :key="image" class="slider-img">
              <span :style="inlineBgImage(image)"></span>
            </div>
          </div>
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
      ],
      team: [
        {
          name: 'Ben',
          image: 'team1.jpg'
        },
        {
          name: 'Sarah',
          image: 'team2.jpg'
        },
        {
          name: 'Emily',
          image: 'team3.jpg'
        },
        {
          name: 'Sam',
          image: 'team4.jpg'
        },
        {
          name: 'Dan',
          image: 'team5.jpg'
        },
        {
          name: 'Michelle',
          image: 'team6.jpg'
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
      ],
      galleryImages: [
        'pourover.jpg',
        'coffee-art.jpg',
        'coffeeshop4.jpg',
        'beans2.jpg'
      ]
    }
  },
  methods: {
    inlineBgImage: function(src) {
      let bgImage = require(`~/assets/images/${src}`);
      return {
        backgroundImage: `url("${bgImage}")`
      }
    }
  }
}
</script>

<style lang="scss">


</style>
