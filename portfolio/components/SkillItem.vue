<template lang="pug">
    div.skill-item.p-3.mx-2
      .skill-logo(:style="skillLogo")
</template>

<script>
export default {
  name: 'SkillItem',
  props: {
    logo: { default: '', type: String }
  },
  computed: {
    skillLogo () {
      return {
        backgroundImage: "url('/skill-logos/" + this.logo + "')"
      }
    }
  }
}
</script>

<style lang="scss" scoped>
  .skill-logo{
    background-size: contain;
    background-repeat: no-repeat;
    background-position: center;
    width: 100%;
    height: 100%;
  }
  .skill-item{
    width: 80px;
    height: 80px;
    @apply shadow mt-3;
    cursor: pointer;
    transition: all ease-in .3s;
  }
  .skill-item:hover{
    @apply shadow-md;
  }
  .skill-tab.is-active{
    @apply border-b-4 border-yellow-500;
  }
</style>
