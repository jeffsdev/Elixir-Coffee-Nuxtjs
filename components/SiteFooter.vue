<template>
    <footer class="site-footer">
        <div class="site-footer__top">
            <div class="footer-logo">
                <img src="~/assets/images/elixir-logo.png" alt="elixir coffee">
                <h2>Elixir Coffee</h2>
            </div>
        </div>
        <div class="site-footer__content">

          <div class="footer-column">
            <div class="footer-tweets">
              <h3>Latest Tweet</h3>
              <p class="tweet">"Roast cream body, turkish, froth sit, aged grounds."</p>
              <p class="tweet-meta">2 days ago - <a href="#" class="link-hover-underline">@elixircoffee</a></p>
            </div>
            <div class="footer-blogposts">
                <h3>Latest Posts</h3>
                <p v-for="post in posts" :key="post">
                    <a href="#" class="link-hover-underline">{{post.title}}</a>
                    <span> - {{post.date}}</span>
                </p>
            </div>
          </div>
          <div class="footer-column">
            <div class="footer-hours">
              <h3>Hours</h3>
              <p>Open 7am - 4pm</p>
            </div>
            <div class="footer-locations">
              <h3>Locations</h3>
              <div v-for="location in locations" :key="location">
                  <h4>{{location.name}}</h4>
                  <span class="address">{{location.address}}</span>
                  <br>
                  <span class="phone">{{location.phone}}</span>
              </div>
            </div>
            <div class="footer-social">
              <a href="#" class="link-hover-underline"><img src="~/assets/images/logo-facebook.svg" alt="facebook"></a>
              <a href="#" class="link-hover-underline"><img src="~/assets/images/logo-yelp.svg" alt="yelp"></a>
              <a href="#" class="link-hover-underline"><img src="~/assets/images/logo-twitter.svg" alt="twitter"></a>
              <a href="#" class="link-hover-underline"><img src="~/assets/images/logo-instagram.svg" alt="instagram"></a>
            </div>
          </div>
          <div class="footer-column">
            <div class="footer-form">
              <h3>Contact</h3>
              <p>Let us know what you think!</p>
              <form id="contact-form">
                <input type="text" placeholder="Name">
                <input type="text" placeholder="Email">
                <textarea placeholder="Subject"></textarea>
                <button type="submit" class="button--default">Send Message</button>
              </form>
            </div>
          </div>
        </div>
        <div class="site-footer__bottom">
          <p><span>&copy;</span> Designed and Coded by Jeff Seymour |
          <a href="https://github.com/jeffsdev/Elixir-Coffee" class="link-hover-underline">View Code on Github</a> |
          <a href="http://www.jeffseymour.me" class="link-hover-underline">View Portfolio</a>
          </p>
        </div>
    </footer>
</template>

<script>
import data from '~/static/data.json';

export default {
    data() {
        return {
            locations: data.locations,
            posts: data.posts
        }
    }
}
</script>

<style lang="scss">
    .site-footer {
      background: $coffee-black;
      padding: 1em 0 0 0;

      &__top {
        padding: 1.5em 2% 3em 2%;
      }

      &__bottom {
          padding: 1em 2%;
          background: #111;
          color: #999;
          text-align: center;
          a:first-of-type {
            display: inline-block;
          }
      }

      .footer-logo {
        display: flex;
        margin: auto;
        justify-content: center;
        align-items: center;

        img {
          max-height: 3em;
          margin-right: 10px;
        }

        h2 {
          padding-top: .5em;
          color: $light-tan;
          font-weight: 100;
          margin: 0;
        }
      }

      &__content {
        display: flex;
        flex-wrap: wrap;

        p,
        span,
        h3 {
          color: $light-tan;
        }
      }

      .footer-column {
        flex: 1 2;
        text-align: center;
        min-width: 40%;
        margin-bottom: 2em;
        padding: 0 1em;
        > div:not(:last-child) {
          margin: 0 0 3em;
        }

        h4 {
          margin: 1em 0 .5em;
          color: $coffee-light;
        }

        @media screen and #{$tablet} {
          min-width: 25%;
        }
      }

      .footer-social {
        img {
          display: inline-block;
          height: 1.5em;
          margin: 1.125em;

          @media screen and #{$tablet} {
            margin: 1em;
          }
        }
      }
    }
</style>