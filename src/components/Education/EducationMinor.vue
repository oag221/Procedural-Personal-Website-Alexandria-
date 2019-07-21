<template>
  <span>
    <span v-if="Minor.length === 1">Minor:</span>
    <span v-if="Minor.length > 1">Minors:</span>
    <span v-for="(minor, minorIndex) in Minor" v-bind:key="'Minor' + minor">
      {{minor}}<span v-if="minorIndex !== Minor.length - 1">,
        <span v-if="minorIndex === Minor.length - 2 && Minor.length > 2">&amp;</span>
      </span>
    </span>
  </span>
</template>

<script lang="ts">
export default {
  name: "EducationMinor",
  props: {
    Minor: Array
  }
};
</script>

<style scoped lang="scss">
</style>
