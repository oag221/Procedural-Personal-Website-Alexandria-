<template>
  <div class="bar">
    <form class="form-inline">
      <label class="my-1 mr-2 subheading" for="inlineFormCustomSelectPref">Why are you here?</label>
      <select class="custom-select my-1 mr-sm-2" id="inlineFormCustomSelectPref">
        <option v-for="(option, index) in About.options" v-bind:key="'callToAction' +  index" :value="index">
          {{option}}
        </option>
      </select>
      <button type="submit" class="btn">Submit</button>
    </form>
  </div>
</template>

<script lang="ts">
export default {
  name: "CallToAction",
  props: {
    About: Object
  }
};
</script>

<style scoped lang="scss">
.bar {
  background-color: #42a5f5;
  color: white;
  padding: 2rem;
}

.subheading {
  color: white;
  display: inline-block;
}

.btn {
  color: #42a5f5;
  background-color: white;
  width: 100px;
}

.custom-select {
  flex: 1;
  min-width: 200px;
}
</style>