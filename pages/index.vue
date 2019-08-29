<template lang="pug">
  div
    section.hero-container
      .hero-content
        .container.mx-auto
          span.hi Hi!
          h1.title Ich bin Linus
          vue-typed-js(:strings="['Software Entwickler ^800', 'VueJs Developer ^800','Problemlöser ^800', 'Go Developer', 'Tech Enthusiast ^800']" :shuffle="true" :backDelay="400" :startDelay="1500" :backSpeed="50" :loopCount="3" :loop="true")
            span.subtitle.text-warning-dark.pr-1 Ein
              span.typing.pl-1
          .flex.mt-4.intro-buttons
            a.button.is-warning.mr-2(@click.prevent="scrollToSkills") Meine Skills
            a.button.is-info(href="mailto:letters@linusboehm.de") Hire Me
      .header-bg.lg_w-1-2(class=" w-screen")
      .go-down(@click.prevent="scrollToSkills")
        i.mdi.mdi-chevron-down
    skills-component(href="skills")
</template>

<script>

import SkillsComponent from '../components/SkillsComponent'
export default {
  name: 'Startseite',
  components: { SkillsComponent },
  data () {
    return {
    }
  },
  methods: {
    scrollToSkills () {
      document.querySelector('#skills').scrollIntoView({
        behavior: 'smooth'
      })
    }

  },
  head () {
    return {
      title: 'Startseite',
      meta: [
        // hid is used as unique identifier. Do not use `vmid` for it as it will not work
        { hid: 'description', name: 'description', content: 'Hi! Ich bin Linus, ein Full-Stack Web Entwickler' }
      ]
    }
  }
}
</script>

<style lang="scss">
  /* Sample `apply` at-rules with Tailwind CSS
  .container {
    @apply min-h-screen flex justify-center items-center text-center mx-auto;
  }
  */
  .go-down{
    @apply text-blue-700;
    font-size: 42px;
    position: absolute;
    bottom: 10px;
    animation: floating 2.5s infinite;
    left: 50%;
    transform: translateX(-50%);
    cursor: pointer;
  }
  .container {
  }
  .intro-buttons{
    width: 280px;
  }
  .header-bg{
    position: absolute;
    height: 100vh;
    background-size: cover;
    background-position: 50% 60%;
    background-image: url("/main-header.jpg");
    z-index: -1;
    right: 0;

  }
  @keyframes floating {
    0% {bottom: 0}
    50% {bottom: 20px}
    100% {bottom: 0}
  }
  .hero-container{
    min-height:  100vh;
  }

  .hi{
    font-size: 20px;
  }
  .title {
    display: block;
    font-weight: 300;
    font-size: 36px;
    letter-spacing: 1px;
  }

  .subtitle {
    font-weight: 300;
    font-size: 22px;
    word-spacing: 2px;
    padding-bottom: 15px;
  }

  .links {
    padding-top: 15px;
  }
</style>
