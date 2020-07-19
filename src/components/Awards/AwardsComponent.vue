<template>
  <section class="resume-section p-3 p-lg-5 d-flex align-items-center" id="awards">
    <div class="w-100">
      <h2 class="mb-2">Awards</h2>
      <ul class="fa-ul mb-0" v-for="(award, index) in Awards" v-bind:key="'Awards' + index">
        <AwardsContent :Award="award" />
      </ul>
    </div>
  </section>
</template>

<script lang="ts">
import AwardsContent from './AwardsContent.vue'

export default {
  name: 'AwardsComponent',
  props: {
    Awards: Array
  },
  components: {
    AwardsContent
  }
}
</script>

<style scoped lang="scss">
section.resume-section {
  min-height: 50vh;
}
</style>
