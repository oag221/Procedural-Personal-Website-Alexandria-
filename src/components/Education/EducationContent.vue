<template>
  <div class="resume-item d-flex flex-column flex-md-row justify-content-between mb-5">
    <div class="resume-content">
      <div class="mb-0 school-name-date">
        <h3 class="school-name">{{education.name}}</h3>
        <span class="resume-date text-md-right school-date">
          <span class="text-primary">{{education.startDate}} - {{education.endDate}}</span>
        </span>
      </div>
      <EducationDegree v-if="education.degrees" :Degrees="education.degrees" />
    </div>
  </div>
</template>

<script lang="ts">
import EducationDegree from './EducationDegree.vue';

export default {
  name: "EducationContent",
  props: {
    education: Object,
    index: Number
  },
  components: {
    EducationDegree
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
