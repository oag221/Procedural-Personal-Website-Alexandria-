<template>
  <h4 class="gpa">
    <span class="mr-5" v-if="GPA.cumulative">Cumulative GPA: {{GPA.cumulative}} / {{GPA.scale}}</span>
    <span v-if="GPA.major">Major GPA: {{GPA.major}} / {{GPA.scale}}</span>
  </h4>
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
.gpa {
  display: flex;
  flex-wrap: wrap;
}

.gpa > span {
  display: inline-block;
  font-weight: 500;
}
</style>
