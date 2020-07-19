<template>
  <section class="resume-section p-3 p-lg-5 d-flex align-items-center" id="projects">
    <div class="w-100">
      <h2 class="mb-2">Projects</h2>
      <div class="projects-wrapper">
        <div v-for="(project, index) in Projects" v-bind:key="'Projects' + index" class="card-wrapper">
          <ProjectCard :project="project" />
        </div>
      </div>
    </div>
  </section>
</template>

<script lang="ts">
import ProjectCard from './ProjectCard.vue'

export default {
  name: 'ProjectComponent',
  props: {
    Projects: Array
  },
  components: {
    ProjectCard
  }
}
</script>

<style scoped lang="scss">
section.resume-section {
  min-height: 50vh;
}

section div div.projects-wrapper {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  justify-content: space-evenly;
}

section div div.interests-wrapper div.card-wrapper {
  padding: 15px;
}
</style>
