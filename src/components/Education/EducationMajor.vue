<template>
  <span class="major mb-2">
    <h4 class="major-text mb-0">
      <span v-if="Major.length === 1">Major:</span>
      <span v-if="Major.length > 1">Majors:</span>
    </h4>
    <span>
      <span v-for="(major, index) in Major" v-bind:key="'Major' + index" class="mr-3 mb-3">
        <a 
          tabindex="0"
          data-trigger="focus"
          role="button" 
          class="btn btn-primary btn-sm"
          data-toggle="popover" 
          :title="major.title" 
          :data-content="major.description">
          {{major.title}}
        </a>
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
.major {
  display: flex;
  align-content: center;
  flex-wrap: wrap;
}

.major-text {
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
