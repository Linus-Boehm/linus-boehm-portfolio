<template lang="pug">
    div.footer-container
      .container.mx-auto.flex.flex-row-reverse
        nuxt-link.footer-link(to="/impressum") Impressum
        nuxt-link.footer-link(to="/datenschutz") Datenschutzerklärung
</template>

<script>
export default {
  name: 'FooterComponent'
}
</script>

<style lang="scss" scoped>
  .footer-container{
    @apply bg-blue-700;
    padding: 8px 20px 8px 20px;
  }
  .footer-link{
    @apply text-white px-2;
    font-weight: 600;
    text-decoration: none;
  }
  .footer-link:hover, .nuxt-link-active{
    text-decoration: underline;
    @apply text-gray-300;

  }
</style>
