<template>
  <div class="resume-item d-flex flex-column flex-md-row justify-content-between mb-5">
    <div class="resume-content">
      <div class="mb-2 school-name-date">
        <h2 class="school-name">
          <span class="bubble-major" v-bind:class="{ complete: education.status === 'complete', current: education.status === 'current' }"></span>
          <div>{{education.name}}</div>
        </h2>
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
  flex-wrap: wrap;
}

.school-name {
  font-size: 2.5rem;
  font-weight: bold;
  margin-bottom: 0;
  display: flex;
}

.school-name div {
  position: relative;
  left: -20px;
}

.school-date {
  font-size: 1.5rem;
  min-width: 0 !important;
}

.bubble-major {
  content: '';
  background-color: white;
  border: 2px solid #2196F3;
  border-radius: 50%;
  height: 20px;
  width: 20px;
  min-height: 20px;
  min-width: 20px;
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
