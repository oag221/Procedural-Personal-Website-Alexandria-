<template>
  <div class="bar">
    <form class="form-inline">
      <label class="my-1 mr-2 subheading" for="inlineFormCustomSelectPref">Why are you here?</label>
      <select v-model="selectedIndex" class="custom-select my-1 mr-sm-2" id="inlineFormCustomSelectPref">
        <option 
          v-for="(option, index) in About.options" 
          v-bind:key="'callToAction' +  index" 
          :value="index"
        >
          {{option}}
        </option>
      </select>
      <a 
        role="button" 
        class="btn js-scroll-trigger" 
        href="#contact" 
        v-on:click="updateContact(selectedIndex)"
      >Submit</a>
    </form>
  </div>
</template>

<script lang="ts">
export default {
  name: 'CallToAction',
  props: {
    About: Object,
    ContactIndex: Number
  },
  data () {
    return {
      selectedIndex: this.ContactIndex
    }
  },
  methods: {
    updateContact (index: Number) {
      this.$emit('updateContact', index)
    }
  }
}
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
  background-color: #fafafa;
  width: 100px;
}

.btn:hover {
  color: #42a5f5;
  background-color: #ffffff;
}

.custom-select {
  flex: 1;
  min-width: 200px;
  cursor: pointer;
}
</style>