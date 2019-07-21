<template>
  <div class="resume-item d-flex flex-column flex-md-row justify-content-between mb-5">
    <div class="resume-content">
      <div class="mb-0 experience-name-date">
        <h3 class="experience-name">{{experience.role}}</h3>
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
}

.experience-name {
  font-size: 2rem;
  font-weight: bold;
}

.experience-date {
  font-size: 1.5rem;
}
</style>
