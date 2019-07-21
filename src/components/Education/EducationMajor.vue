<template>
  <span>
    <span v-if="Major.length === 1">Major:</span>
    <span v-if="Major.length > 1">Majors:</span>
    <span v-for="(major, majorIndex) in Major" v-bind:key="'Major' + major">
      {{major}}<span v-if="majorIndex !== Major.length - 1">,
        <span v-if="majorIndex === Major.length - 2 && Major.length > 2">&amp;</span>
      </span>
    </span>
  </span>
</template>

<script lang="ts">
export default {
  name: "EducationMajor",
  props: {
    Major: Array
  }
};
</script>

<style scoped lang="scss">
</style>
