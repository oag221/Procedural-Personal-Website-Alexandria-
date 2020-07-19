<template>
  <section class="resume-section p-3 p-lg-5" id="tech">
    <h2 class="mb-2">Technical Skills</h2>
    <div class="wrapper w-100 d-lg-flex d-sm-flex align-items-center">
      <div class="skill-container pr-2">
        <SkillsCard :skill="Skills.catalog[activeIndex]"/>
      </div>
      <div class="skill-groups mn-50 pl-2">
        <div v-for="(skillset, index) in SkillList" v-bind:key="'Skill' + index">
          <SkillsSkillset :skillset="skillset" :activeIndex="activeIndex" @toggleActivated="setActiveIndex" />
        </div>
      </div>
    </div>
    <SkillsBullets :Bullets="Skills.bullets" />
  </section>
</template>

<script lang="ts">
import SkillsSkillset from './SkillsSkillset.vue'
import SkillsCard from './SkillsCard.vue'
import SkillsBullets from './SkillsBullets.vue'

export default {
  name: 'SkillsComponent',
  props: {
    Skills: Object
  },
  components: {
    SkillsSkillset,
    SkillsCard,
    SkillsBullets
  },
  data () {
    return {
      activeIndex: this.getRandomIndex()
    }
  },
  computed: {
    SkillList () {
      return this.Skills.skillsets.map((skillset) => {
        skillset.skills = skillset.skills.map((skillId) => {
          let index
          const skillObj = this.Skills.catalog.filter((item, idx) => {
            if (item.id === skillId) {
              index = idx
              return true
            }
            return false
          })[0]
          skillObj.index = index
          return skillObj
        })
        return { ...skillset }
      })
    }
  },
  methods: {
    setActiveIndex (index: Number) {
      this.activeIndex = index
    },
    getRandomIndex (): Number {
      return Math.floor(Math.random() * this.Skills.catalog.length)
    }
  }
}
</script>

<style scoped lang="scss">
section.resume-section {
  min-height: 50vh;
}

.wrapper.d-sm-flex {
  flex-direction: column;
}

.wrapper.d-lg-flex {
  flex-direction: row;
  justify-content: flex-start;
}

.wrapper.d-lg-flex div {
  flex: 1 1 0;
}

.skill-container {
  align-self: flex-start;
}

.skill-groups {
  align-self: flex-start;
}
</style>
