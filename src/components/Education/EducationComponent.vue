<template>
  <section class="resume-section p-3 p-lg-5 d-flex align-items-center" id="education">
    <div class="w-100">
      <h2 class="mb-2 education-header">Education</h2>
      <div class="education-body pl-4">
        <div v-for="(education, index) in EducationList" v-bind:key="'EducationList' + index">
          <EducationContent :education="education" :index="index" />
          <hr v-if="index !== EducationList.length - 1" />
        </div>
      </div>
    </div>
  </section>
</template>

<script lang="ts">
import EducationContent from "./EducationContent.vue";

export default {
  name: "EducationComponent",
  props: {
    EducationList: Array
  },
  components: {
    EducationContent
  }
}
</script>

<style scoped lang="scss">
section.resume-section {
  min-height: 50vh;
}

.education-body {
  border-left: 3px dashed #2196F3;
}

.education-body > div {
  position: relative;
  top: -14px;
}
</style>
