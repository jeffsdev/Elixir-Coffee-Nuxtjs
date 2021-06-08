<template>
  <a href="#elixir-coffee" class="brand-logo">
    <img src="~/assets/images/elixir-logo.svg" alt="Elixir Coffee">
    <h1>Elixir Coffee</h1>
  </a>
</template>

<style lang="scss">
.brand-logo {
    display: flex;
    align-items: center;
    height: 100%;
    color: $light-tan;
    img {
      height: 75%;
      margin-right: .625em;
      transition: .3s;
      object-fit: contain;
    }
    h1 {
        position: relative;
        top: .125em;
        font-size: 1em;
        font-weight: normal;
        line-height: 1;
        width: 50%;
        transition: .3s;
        @media screen and #{$tablet} and (min-height: 640px) {
          font-size: 1.5em;
        }
    }
}
</style>
