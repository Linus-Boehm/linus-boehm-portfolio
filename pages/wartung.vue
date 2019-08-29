<template lang="pug">
  section.wartung
    .hero-container
      .hero-content
        .container.mx-auto.p-10.wartung-content.rounded.bg-white(class="lg:bg-transparent shadow-md lg:shadow-none")
          h2 Dieser Inhalt befindet sich zurzeit im Aufbau
          nuxt-link.btn-info-outline.btn.mt-4(to="/") Zurück zur Startseite
      .wartung-bg(class="lg:w-1/2 w-screen")

</template>

<script>
export default {
  name: 'Wartung'
}
</script>

<style lang="scss" scoped>
  section.wartung{
    width: 100%;

  }
  .hero-container, section.wartung{
    min-height: 100vh;
  }
  .wartung-bg{
    position: absolute;
    background-image: url("/maintenance.jpg");
    height: 100vh;
    right: 0;
    background-position: 50% 70%;
    background-size: cover;
    background-repeat: no-repeat;
    z-index: -1;
  }
</style>
