<template>
  <div class="degree-container">
    <div v-for="(degree, index) in Degrees" v-bind:key="index" class="degree-divider">
      <div v-if="degree.degree" class="degree-header mb-1 mt-2">
        <span class="degree subheading">
          <span class="bubble-minor" v-bind:class="{ complete: degree.status === 'complete', current: degree.status === 'current' }"></span>
          <div>{{degree.degree}}</div>
        </span>
        <span class="expected-date">Expected: {{degree.expected}}</span>
      </div>

      <div class="degree-body">
        <div class="detail-attributes mb-2">
          <EducationGPA v-if="degree.gpa" :GPA="degree.gpa"/>
          <EducationMajor v-if="degree.major" :Major="degree.major"/>
          <EducationMinor v-if="degree.minor" :Minor="degree.minor"/>
          <EducationCertificate v-if="degree.certificate" :Certificate="degree.certificate"/>
          <div
            class="mt-4"
            v-for="(descParagraphh, degreeIdx) in degree.description"
            v-bind:key="'EducationList' + index + 'Description' + degreeIdx"
          >{{descParagraphh.text}}</div>
          <EducationCourses v-if="degree.courses" :Courses="degree.courses" />
        </div>
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
import EducationCourses from './EducationCourses.vue';

export default {
  name: "EducationDegree",
  props: {
    Degrees: Array
  },
  components: {
    EducationMajor,
    EducationMinor,
    EducationCertificate,
    EducationGPA,
    EducationCourses
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
  flex-wrap: wrap;
}

.expected-date {
  align-self: center;
  font-size: 1.25rem;
}

.bubble-minor {
  content: '';
  background-color: white;
  border: 2px solid #2196F3;
  border-radius: 50%;
  height: 16px;
  width: 16px;
  min-height: 16px;
  min-width: 16px;
  padding-left: 0px;
  left: -33px;
  margin-top: 16px;
  position: relative;
  display: inline-block;
  align-self: start;
}

.complete {
  background-color: #2196F3;
}

.current {
  animation: blink 1s infinite alternate;
}

@keyframes blink {
  from { background-color: white; }
  to { background-color: #2196F3; }
}

.degree.subheading {
  display: flex;
  font-weight: 500;
  font-size: 2rem;
}

.degree.subheading div {
  position: relative;
  left: -16px;
}
</style>
