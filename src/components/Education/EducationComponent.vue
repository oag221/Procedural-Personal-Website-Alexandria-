<template>
  <section class="resume-section p-3 p-lg-5 d-flex align-items-center" id="education">
    <div class="w-100">
      <h2 class="mb-2 education-header">Education</h2>

      <div class="education-body pl-4">
        <div v-for="(education, index) in EducationList" v-bind:key="'EducationList' + index" class="major">
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

div.major::before {
  background: white;
  display: inline-block;
  position: absolute;
  border-radius: 50%;
  border: 3px solid #22c0e8;
  left: 20px;
  width: 20px;
  height: 20px;
}

div.education-body {
  border-left: 2px dashed #2196F3;
}

div.education-body div.major::before {
  background-color: white;
  border: 2px solid #2196F3;
  border-radius: 50%;
  height: 20px;
  width: 20px;
  padding-left: 0px;
  position: relative;
}
</style>
