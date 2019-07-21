<template>
  <span v-if="Certificate">
    <span v-if="Certificate.length === 1">Certificate:</span>
    <span v-if="Certificate.length > 1">Certificates:</span>
    <span v-for="(certificate, certIndex) in Certificate" v-bind:key="'Certificate' + certificate">
      {{certificate}}<span v-if="certIndex !== Certificate.length - 1">,
        <span v-if="certIndex === Certificate.length - 2 && Certificate.length > 2">&amp;</span>
      </span>
    </span>
  </span>
</template>

<script lang="ts">
export default {
  name: "EducationCertificate",
  props: {
    Certificate: Array
  }
};
</script>

<style scoped lang="scss">
</style>
