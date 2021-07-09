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