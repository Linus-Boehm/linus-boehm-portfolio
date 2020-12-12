<template lang="pug">
  b-navbar
    template(slot="brand")
        b-navbar-item(tag="nuxt-link" :to="{ path: '/admin/' }")
            img.mx-auto( src="/logo.svg")
    template(slot="start")
        b-navbar-item(tag="nuxt-link" :to="{ path: '/admin/' }")
            Dashboard
    nav.mainnav.z-50.bg-white(:class="{ 'lg:bg-transparent': true, 'nav-shrinked': isShrinked}")
      .mainnav-container.flex.p-2
        .menu-hamburger.relative
          a.hamburger.hamburger--squeeze( @click.prevent="menuToggle = !menuToggle" :class="{'is-active': menuToggle}" aria-label="Menu" aria-controls="navigation" :aria-expanded="menuToggle")
            span.hamburger-box
              span.hamburger-inner
        .login-button.ml-auto.pt-3.mr-4(class="md:visible invisible")
          nuxt-link.btn.btn-info(to="/login") Login

      nuxt-link(to="/").main-logo
        img.mx-auto( src="/logo.svg")
    nav.sidenav.z-20( :class="{'is-active': menuToggle}")
      .sidenav-inner.flex.flex-col
        h2.pl-5 MENU
        .nav-items.mt-6(@click="menuToggle=false")

          nuxt-link.nav-item(to="/" exact) Startseite

          nuxt-link.nav-item(to="/wartung" exact) Über Mich

          //nuxt-link.nav-item(to="/wartung" exact) Lösungen

          //nuxt-link.nav-item(to="/wartung" exact) Portfolio

          //nuxt-link.nav-item(to="/wartung" exact) Blog

</template>

<script>
export default {
  name: 'AdminHeaderMenu',

  data () {
    return {
      menuToggle: false,
      isShrinked: false
    }
  },
  mounted () {
  }
}
</script>

<style lang="scss" scoped>
  .nav-item{
    display: block;
    padding: 15px 10px 15px 20px;
    @apply font-sans text-gray-700 border-r-8 border-transparent bg-transparent;
    text-decoration: none;
    letter-spacing: 1px;
    text-transform: uppercase;
    width: 100%;
    font-size: 1.1em;
    transition: all ease .4s;

  }
  .mainnav.nav-shrinked{
    background-color: white !important;
    box-shadow: 0 2px 16px 0 rgba(29, 31, 55, 0.21)
  }

  .mainnav.nav-shrinked .main-logo img{
    @apply w-2-3;
    margin-left: 16.667%;
  }
  @media (max-width: 768px) {
    .mainnav{
      background-color: white !important;
      box-shadow: 0 2px 16px 0 rgba(29, 31, 55, 0.21)
    }
    .mainnav .main-logo img{
      @apply w-2-3;
      margin-left: 16.667%;
    }
  }
  .nav-item.nuxt-link-active{
    @apply border-blue-700;
  }
  .nav-item:hover, .nav-item.nuxt-link-active {
    @apply bg-gray-200 text-gray-700 ;
  }
  .nav-item:hover {

    @apply border-yellow-400;

  }

  .sidenav {
    position: fixed;
    height: 100vh;
    width: 300px;

    top: 0;
    padding-top: 85px;
    left: 0;
    margin-left: -305px;
    transition: margin-left ease-in-out .5s;
    background-color: #FFF;
    box-shadow: 2px 0 16px 0 rgba(29, 31, 55, 0.21);

  }

  .sidenav.is-active {
    margin-left: 0;
  }

  .mainnav {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    transition: all ease-in-out .2s;

    box-shadow: 0 2px 16px 0 rgba(29, 31, 55, 0)

  }

  .mainnav-container {
    width: 100%;
    position: relative;
  }

  .main-logo {
    width: 80px;
    display: block;
    position: absolute;
    left: 50%;
    top: 25px;
    transform: translateX(-50%);
  }
  .main-logo:hover img{
    transform: scale(1.05);
    opacity: .8;
  }
  .main-logo img{
    margin-left: 0;
    width: 100%;
    transition: all ease .6s;
  }

  .menu-hamburger {

  }
</style>
