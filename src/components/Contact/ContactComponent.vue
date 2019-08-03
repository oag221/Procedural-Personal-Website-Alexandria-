<template>
  <section class="resume-section p-3 p-lg-5 d-flex align-items-center" id="contact">
    <div class="w-100">
      <h2 class="mb-2">Contact</h2>
      <form>
        <div class="form-group">
          <label class="subheading" for="exampleInputEmail1">Why are you here?</label>
          <div v-for="(option, index) in About.options" v-bind:key="'FormOption' + index" class="form-check">
            <input class="form-check-input" type="radio" name="gridRadios" id="gridRadios1" value="option1" checked>
            <label class="form-check-label" for="gridRadios1">
              {{option}}
            </label>
          </div>
        </div>
        <div class="form-group">
          <label class="subheading" for="exampleFormControlTextarea1">Message</label>
          <textarea 
            class="form-control" 
            id="exampleFormControlTextarea1" 
            rows="3" 
            placeholder="Send me a message..."></textarea>
        </div>
        <button type="submit" class="btn btn-xl">Submit</button>
      </form>
    </div>
  </section>
</template>

<script lang="ts">
import ContactComponent from './ContactComponent.vue';

export default {
  name: "ContactComponent",
  props: {
    About: Object
  }
}
</script>

<style scoped lang="scss">
section.resume-section {
  min-height: 50vh;
  color: white;
  background-color: #42a5f5;
}

div.w-100 {
  padding-bottom: 3rem;
}

h2 {
  color: white;
}

.btn {
  color: #42a5f5;
  background-color: #f0f0f0;
  width: 100px;
}

.btn:hover {
  color: #42a5f5;
  background-color: #ffffff;
}

.form-check-label {
  font-size: 1.25rem;
}

.subheading {
  margin: 0;
}
</style>
