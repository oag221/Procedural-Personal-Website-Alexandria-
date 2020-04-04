<template>
  <span class="minor mb-2">
    <h5 class="minor-text mb-0">
      <span v-if="Minor.length === 1">Minor:</span>
      <span v-if="Minor.length > 1">Minors:</span>
    </h5>
    <span>
      <span v-for="(minor, index) in Minor" v-bind:key="'Minor' + index" class="mr-3 mb-3">
        <a 
          tabindex="0"
          data-trigger="focus"
          role="button" 
          class="btn btn-primary btn-sm"
          data-toggle="popover" 
          :title="minor.title" 
          :data-content="minor.description">
          {{minor.title}}
        </a>
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
.minor {
  display: flex;
  align-content: center;
  flex-wrap: wrap;
}

.minor-text {
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
