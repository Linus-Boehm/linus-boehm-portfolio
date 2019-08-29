<template lang="pug">
    section.hero-container
      .hero-content
        .container.mx-auto
          h2#skills Meine Skills
          ul.list-reset.flex.skill-tabs.mt-6.flex-wrap
            li.mr-1.skill-tab(:class="{'is-active': selectedSkill === 0}" @click="selectedSkill = 0")
              .tab-item
                span.mdi.mdi-desktop-mac
                span All
            li.mr-1.skill-tab(:class="{'is-active': selectedSkill === 2}" @click="selectedSkill = 2")
              .tab-item
                span.mdi.mdi-xml
                span Backend Languages
            li.mr-1.skill-tab(:class="{'is-active': selectedSkill === 1}" @click="selectedSkill = 1")
              .tab-item
                span.mdi.mdi-vuejs
                span Frontend
            li.mr-1.skill-tab(:class="{'is-active': selectedSkill === 3}" @click="selectedSkill = 3")
              .tab-item
                span.mdi.mdi-apple-keyboard-command
                span Frameworks
          .flex.flex-row.flex-wrap
            skill-item(v-show="showSkill(2)" logo="go.svg" data-tooltip="{content:'GoLang', trigger: 'hover click'}")
            skill-item(v-show="showSkill(2)" logo="php.svg" data-tooltip="{content: 'PHP', trigger: 'hover click' }")
            skill-item(v-show="showSkill(2)" logo="node.svg" data-tooltip="{content: 'Node.js', trigger: 'hover click' }")
            skill-item(v-show="showSkill(1)" logo="vue.svg" data-tooltip="{content: 'Vue.js', trigger: 'hover click' }")
            skill-item(v-show="showSkill(1)" logo="js.png" data-tooltip="{content: 'JavaScript', trigger: 'hover click' }")
            skill-item(v-show="showSkill(3)" logo="nuxt.jpg" data-tooltip="{content: 'Nuxt.js', trigger: 'hover click' }")
            skill-item(v-show="showSkill(3)" logo="laravel.svg" data-tooltip="{content: 'Laravel', trigger: 'hover click' }")
            skill-item(v-show="showSkill(3)" logo="gobuffalo.svg" data-tooltip="{content: 'goBuffalo', trigger: 'hover click' }")
            skill-item(v-show="showSkill(3)" logo="wordpress.png" data-tooltip="{content: 'Wordpress', trigger: 'hover click' }")
            skill-item(v-show="showSkill(3)" logo="statamic.svg" data-tooltip="{content: 'Statamic', trigger: 'hover click' }")
</template>

<script>
import SkillItem from './SkillItem'
export default {
  name: 'SkillsComponent',
  components: { SkillItem },
  data () {
    return {
      selectedSkill: 0
    }
  },
  methods: {
    showSkill (showAt) {
      return this.selectedSkill === 0 || showAt === this.selectedSkill
    }
  }
}
</script>

<style lang="scss" scoped>

  .tab-item{
    @apply bg-white inline-block rounded-t py-2 px-4 text-blue-700 font-semibold;
    cursor: pointer;
  }
  .tab-item .mdi{
    margin-right: 4px;
  }
  .tab-item:hover, .is-active .tab-item{
    @apply text-blue-700;
  }
  .skill-tab {
    @apply border-b-2 border-transparent;
    transition: all ease-in .3s;
  }
  .skill-tab.is-active{
    @apply border-yellow-500;
  }
  .is-active .tab-item{

  }
  .hero-container{
    min-height: 50vh;
  }
</style>
