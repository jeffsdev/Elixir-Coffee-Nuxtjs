<template>
    <section class="hero-video">
        <div class="hero-content">
            <h1>
                <span>ELIXIR</span>
                <span>coffee</span>
                <span>- Portland, OR -</span>
            </h1>
        </div>
        <div class="video-container height-fix">
            <video id="herovideo" :poster="require('~/assets/images/transparent.png')" autoplay muted loop>
                <source src="~/assets/coffee-bgvid1.mp4" type="video/mp4">
            </video>
        </div>
    </section>
</template>

<script>
export default {
    
}
</script>

<style lang="scss">
.hero-video {
    position: relative;
    max-width: 100vw;
    background: #979797 url("~/assets/images/coffee-bw.jpg") center/cover no-repeat;
    animation: 1s ease-in-out forwards fadeIn;  
  .hero-content {
    position: absolute;
    display: flex;
    flex-direction: column;
    justify-content: center;
    text-align: center;
    padding-top: 5em;
    width: 100%;
    height: 100%;
    z-index: 9999;
    h1 {
        font-size: 1rem;
        line-height: 1;
        @media screen and #{$large} {
            font-size: 1.5rem;
        }
        span {
            display: block;
            text-align: center;
            opacity: 0;
            font-weight: 400;
            text-shadow: .025em .025em .05em $coffee-black;
            animation: 1s ease-in-out forwards fadeIn;  
        }
        span:nth-child(1) {
            font-size: 6em;
            color: $light-tan;
            animation-delay: 1.25s;
        }
        span:nth-child(2) {
            font-size: 4em;
            color: $coffee-black;
            animation-delay: 1.5s;
        }
        span:nth-child(3) {
            margin-top: 1em;
            color: $coffee-light;
            font-size: 1.5em;
            animation-delay: 1.75s;    
            display: inline-block;
            background: rgba(0, 0, 0, 0.65);
            padding: .5em 2em .4em;
            line-height: 1;
            font-weight: 700;
            border: 2px solid;     
        }
    }
  }
  .video-container {
    overflow: hidden;
    height: 100vh;
    #herovideo {
      display: block;
      min-height: 100%;
      max-height: 100vh;
      min-width: 100vw;
      max-width: 100vw;
      overflow-x: hidden;
      opacity: 0;
      object-fit: cover;
      object-position: center;
      animation: 1s ease-in-out 1s forwards fadeIn;    
    }
    @media screen and #{$tablet} {
      min-height: 540px;
      max-height: 35vw;
    }
  }
}

@keyframes fadeIn {
    from {
        opacity: 0;
    }
    to {
        opacity: 1;
    }
}
</style>