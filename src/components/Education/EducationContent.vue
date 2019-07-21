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
      <span v-if="education.major">
        <span v-if="education.major.length === 1">Major:</span>
        <span v-if="education.major.length > 1">Majors:</span>
        <span
          v-for="(major, majorIndex) in education.major"
          v-bind:key="education.name + 'Major' + major"
        >
          {{major}}
          <span v-if="majorIndex !== education.major.length - 1">
            ,
            <span
              v-if="majorIndex === education.major.length - 2 && education.major.length > 2"
            >&amp;</span>
          </span>
        </span>
      </span>
      <div v-if="education.minor">
        <span v-if="education.minor.length === 1">Minor:</span>
        <span v-if="education.minor.length > 1">Minors:</span>
        <span
          v-for="(minor, minorIndex) in education.minor"
          v-bind:key="education.name + 'Minor' + minor"
        >
          {{minor}}
          <span v-if="minorIndex !== education.minor.length - 1">
            ,
            <span
              v-if="minorIndex === education.minor.length - 2 && education.minor.length > 2"
            >&amp;</span>
          </span>
        </span>
      </div>
      <div v-if="education.certificate">
        <span v-if="education.certificate.length === 1">Certificate:</span>
        <span v-if="education.certificate.length > 1">Certificates:</span>
        <span
          v-for="(certificate, certIndex) in education.certificate"
          v-bind:key="education.name + 'Certificate' + certificate"
        >
          {{certificate}}
          <span v-if="certIndex !== education.certificate.length - 1">
            ,
            <span
              v-if="certIndex === education.certificate.length - 2 && education.certificate.length > 2"
            >&amp;</span>
          </span>
        </span>
      </div>
      <div v-if="education.gpa">
        <span
          v-if="education.gpa.cumulative"
        >Cumulative GPA: {{education.gpa.cumulative}} / {{education.gpa.scale}}</span>
        <span
          v-if="education.gpa.major"
        >Major GPA: {{education.gpa.major}} / {{education.gpa.scale}}</span>
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
export default {
  name: "EducationContent",
  props: {
    education: Object,
    index: Number
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
</style>
