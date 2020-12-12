<template lang="pug">
  div.content-wrapper
    header-menu
      client-only
        notifications(group="alerts" position="bottom right")
    .flex-1
      nuxt
    footer-component.footer
</template>
<script>
import FooterComponent from '@/portfolio/components/layout/FooterComponent'
import HeaderMenu from '@/portfolio/components/layout/HeaderMenu'

export default {
  components: { FooterComponent, HeaderMenu }

}
</script>
<style>
  html, body, .content-wrapper, #__layout, #__nuxt {
    height: 100%;
  }
  html, body{
    @apply font-sans;
    scroll-behavior: smooth;
  }
  .content-wrapper {
    display: flex;
    flex-direction: column;
  }
  .content {
    flex: 1 0 auto;
  }
  .footer {
    flex-shrink: 0;
  }
  *,
  *:before,
  *:after {
    box-sizing: border-box;
    margin: 0;
  }
</style>
