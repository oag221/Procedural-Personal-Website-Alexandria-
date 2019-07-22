<template>
  <section class="resume-section p-3 p-lg-5 d-flex align-items-center" id="skills">
    <div class="w-50">
      <h2 class="mb-2">Skills</h2>

      <div v-for="(skillset, index) in Skills.list" v-bind:key="'Skill' + index">
        <SkillsSkillset :skillset="skillset" :index="index" />
      </div>

      <div class="subheading mb-3">Workflow</div>
      <ul class="fa-ul mb-0">
        <li>
          <i class="fa-li fa fa-check"></i>
          Mobile-First, Responsive Design
        </li>
        <li>
          <i class="fa-li fa fa-check"></i>
          Cross Browser Testing &amp; Debugging
        </li>
        <li>
          <i class="fa-li fa fa-check"></i>
          Cross Functional Teams
        </li>
        <li>
          <i class="fa-li fa fa-check"></i>
          Agile Development &amp; Scrum
        </li>
      </ul>
    </div>
    <div class="w-50">
      <SkillsCard :skill="Skills.catalog[activeIndex]"/>
    </div>
  </section>
</template>

<script lang="ts">
import SkillsSkillset from './SkillsSkillset.vue';
import SkillsCard from './SkillsCard.vue';

export default {
  name: "SkillsComponent",
  props: {
    Skills: Object
  },
  components: {
    SkillsSkillset,
    SkillsCard
  },
  data: () => {
    return {
      activeIndex: 1
    }
  }
}
</script>

<style scoped lang="scss">
section.resume-section {
  min-height: 50vh;
}
</style>
