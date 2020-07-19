<template>
  <span class="certificate mb-2">
    <h5 class="certificate-text mb-0">
      <span v-if="Certificate.length === 1">Certificate:</span>
      <span v-if="Certificate.length > 1">Certificates:</span>
    </h5>
    <span>
      <span v-for="(certificate, index) in Certificate" v-bind:key="'Certificate' + index" class="mr-3 mb-3">
        <a 
          tabindex="0"
          data-trigger="focus"
          role="button" 
          class="btn btn-primary btn-sm"
          data-toggle="popover" 
          :title="certificate.title" 
          :data-content="certificate.description">
          {{certificate.title}}
        </a>
      </span>
    </span>
  </span>
</template>

<script lang="ts">
export default {
  name: 'EducationCertificate',
  props: {
    Certificate: Array
  }
}
</script>

<style scoped lang="scss">
.certificate {
  display: flex;
  align-content: center;
  flex-wrap: wrap;
}

.certificate-text {
  display: inline-block;
  font-weight: 500;
  width: 15%;
  min-width: 75px;
}

a.btn, a.btn:focus {
  cursor: pointer;
  color: white !important;
}

a.btn:hover {
  color: #2196F3 !important;
}
</style>

