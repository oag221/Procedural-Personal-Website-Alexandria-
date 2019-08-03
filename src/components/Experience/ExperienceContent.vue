<template>
  <div class="resume-item d-flex flex-column flex-md-row justify-content-between">
    <div class="resume-content">
      <div class="mb-2 experience-name-date">
        <h3 class="experience-name">
          <span class="bubble-major" v-bind:class="{ complete: experience.status === 'complete', current: experience.status === 'current' }"></span>
          <div>{{experience.role}}</div>
        </h3>
        <span class="resume-date text-md-right experience-date">
          <span class="text-primary">{{experience.startDate}} - {{experience.endDate}}</span>
        </span>
      </div>
      <div class="subheading mb-1" v-if="experience.company">{{experience.company}}</div>
      <div v-if="experience.certificate">
        <span v-if="experience.certificate.length === 1">Certificate:</span>
        <span v-if="experience.certificate.length > 1">Certificates:</span>
        <span
          v-for="(certificate, certIndex) in experience.certificate"
          v-bind:key="experience.name + 'Certificate' + certificate"
        >
          {{certificate}}
          <span v-if="certIndex !== experience.certificate.length - 1">
            ,
            <span
              v-if="certIndex === experience.certificate.length - 2 && experience.certificate.length > 2"
            >&amp;</span>
          </span>
        </span>
      </div>
      <div
        class="mt-4"
        v-for="(descParagraphh, experienceIdx) in experience.description"
        v-bind:key="'ExperienceList' + index + 'Description' + experienceIdx"
      >{{descParagraphh.text}}</div>
      <ul>
        <li
          v-for="(bullet, bulletIndex) in experience.bullets"
          v-bind:key="'ExperienceList' + index + 'Bullets' + bulletIndex"
        >{{bullet}}</li>
      </ul>
    </div>
  </div>
</template>

<script lang="ts">
export default {
  name: "ExperienceContent",
  props: {
    experience: Object,
    index: Number
  }
};
</script>

<style scoped lang="scss">
div.resume-content {
  width: 100%;
}

.experience-name-date {
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
}

.experience-name {
  font-size: 2.5rem;
  font-weight: bold;
  margin-bottom: 0;
  display: flex;
}

.experience-name div {
  position: relative;
  left: -20px;
}

.subheading {
  display: flex;
  font-weight: 500;
  font-size: 2rem;
}

.experience-date {
  font-size: 1.5rem;
}

.bubble-major {
  content: '';
  background-color: white;
  border: 2px solid #2196F3;
  border-radius: 50%;
  height: 20px;
  width: 20px;
  padding-left: 0px;
  left: -35px;
  margin-top: 14px;
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
</style>
