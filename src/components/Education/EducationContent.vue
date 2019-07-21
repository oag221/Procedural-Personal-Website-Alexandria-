<template>
  <div class="resume-item d-flex flex-column flex-md-row justify-content-between mb-5">
    <div class="resume-content">
      <div class="mb-0 school-name-date">
        <h3 class="school-name">{{education.name}}</h3>
        <span class="resume-date text-md-right school-date">
          <span class="text-primary">{{education.startDate}} - {{education.endDate}}</span>
        </span>
      </div>
      <div class="subheading mb-1" v-if="education.degree">{{education.degree}}</div>
      <div class="detail-attributes">
        <EducationMajor v-if="education.major" :Major="education.major"/>
        <EducationGPA v-if="education.gpa" :GPA="education.gpa"/>
        <EducationMinor v-if="education.minor" :Minor="education.minor"/>
        <EducationCertificate v-if="education.certificate" :Certificate="education.certificate"/>
      </div>
      <div
        class="mt-4"
        v-for="(descParagraphh, educationIdx) in education.description"
        v-bind:key="'EducationList' + index + 'Description' + educationIdx"
      >{{descParagraphh.text}}</div>
    </div>
  </div>
</template>

<script lang="ts">
import EducationMajor from './EducationMajor.vue';
import EducationMinor from './EducationMinor.vue';
import EducationCertificate from './EducationCertificate.vue';
import EducationGPA from './EducationGPA.vue';

export default {
  name: "EducationContent",
  props: {
    education: Object,
    index: Number
  },
  components: {
    EducationMajor,
    EducationMinor,
    EducationCertificate,
    EducationGPA
  }
}
</script>

<style scoped lang="scss">
div.resume-content {
  width: 100%;
}

.school-name-date {
  display: flex;
  justify-content: space-between;
}

.school-name {
  font-size: 2rem;
  font-weight: bold;
}

.school-date {
  font-size: 1.5rem;
}

.detail-attributes {
  display: flex;
  flex-direction: column;
}
</style>
