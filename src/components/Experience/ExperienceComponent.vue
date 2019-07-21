<template>
  <section class="resume-section p-3 p-lg-5 d-flex justify-content-center" id="experience">
    <div class="w-100">
      <h2 class="mb-2">Experience</h2>

      <div v-for="(experience, index) in ExperienceList" v-bind:key="'ExperienceList' + index">
        <ExperienceContent :experience="experience" :index="index" />
        <hr v-if="index !== ExperienceList.length - 1" />
      </div>
    </div>
  </section>
</template>

<script lang="ts">
import ExperienceContent from './ExperienceContent.vue'

export default {
  name: "ExperienceComponent",
  props: {
    ExperienceList: Array
  },
  components: {
    ExperienceContent
  }
}
</script>

<style scoped lang="scss">
section.resume-section {
  min-height: 50vh;
}
</style>
