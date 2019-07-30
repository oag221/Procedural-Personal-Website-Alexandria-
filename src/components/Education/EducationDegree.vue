<template>
  <div class="degree-container">
    <div v-for="(degree, index) in Degrees" v-bind:key="index">
      <div v-if="degree.degree" class="degree-header mb-1 mt-2">
        <span class="degree subheading">{{degree.degree}}</span>
        <span class="expected-date">Expected: {{degree.expected}}</span>
      </div>

      <div class="detail-attributes mb-2">
        <EducationMajor v-if="degree.major" :Major="degree.major"/>
        <EducationGPA v-if="degree.gpa" :GPA="degree.gpa"/>
        <EducationMinor v-if="degree.minor" :Minor="degree.minor"/>
        <EducationCertificate v-if="degree.certificate" :Certificate="degree.certificate"/>
        <div
          class="mt-4"
          v-for="(descParagraphh, degreeIdx) in degree.description"
          v-bind:key="'EducationList' + index + 'Description' + degreeIdx"
        >{{descParagraphh.text}}</div>
      </div>
      <hr v-if="index !== Degrees.length - 1" class="m-0" />
    </div>
  </div>

</template>

<script lang="ts">
import EducationMajor from './EducationMajor.vue';
import EducationMinor from './EducationMinor.vue';
import EducationCertificate from './EducationCertificate.vue';
import EducationGPA from './EducationGPA.vue';

export default {
  name: "EducationDegree",
  props: {
    Degrees: Array
  },
  components: {
    EducationMajor,
    EducationMinor,
    EducationCertificate,
    EducationGPA
  }
};
</script>

<style scoped lang="scss">
.detail-attributes {
  display: flex;
  flex-direction: column;
}

.degree-header {
  display: flex;
  justify-content: space-between;
}

.expected-date {
  justify-self: flex-end;
}
</style>
