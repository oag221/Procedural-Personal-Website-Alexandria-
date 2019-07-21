<template>
  <section class="resume-section p-3 p-lg-5 d-flex align-items-center" id="skills">
    <div class="w-100">
      <h2 class="mb-2">Skills</h2>

      <div v-for="(skillset, index) in SkillsList.list" v-bind:key="'Skill' + index">
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
  </section>
</template>

<script lang="ts">
import SkillsSkillset from './SkillsSkillset.vue';

export default {
  name: "SkillsComponent",
  props: {
    SkillsList: Array
  },
  components: {
    SkillsSkillset
  }
}
</script>

<style scoped lang="scss">
section.resume-section {
  min-height: 50vh;
}
</style>
