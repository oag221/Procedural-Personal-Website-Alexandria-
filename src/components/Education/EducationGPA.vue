<template>
  <span>
    <span v-if="GPA.cumulative">Cumulative GPA: {{GPA.cumulative}} / {{GPA.scale}}</span>
    <span class="ml-5" v-if="GPA.major">Major GPA: {{GPA.major}} / {{GPA.scale}}</span>
  </span>
</template>

<script lang="ts">
export default {
  name: "EducationGPA",
  props: {
    GPA: Object
  }
};
</script>

<style scoped lang="scss">
</style>
