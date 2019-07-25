<template>
  <section class="resume-section p-3 p-lg-5 d-flex align-items-center" id="interests">
    <div class="w-100">
      <h2 class="mb-5">Interests</h2>
      <div class="interests-wrapper">
        <div v-for="(interest, index) in Interests" v-bind:key="'Interests' + index">
          <InterestsCard :Interest="interest" />
        </div>
      </div>
    </div>
  </section>
</template>

<script lang="ts">
import InterestsCard from './InterestsCard.vue';

export default {
  name: "InterestsComponent",
  props: {
    Interests: Array
  },
  components: {
    InterestsCard
  }
}
</script>

<style scoped lang="scss">
section.resume-section {
  min-height: 50vh;
}

.interests-wrapper {
  display: flex;
  flex-direction: row;
}
</style>
