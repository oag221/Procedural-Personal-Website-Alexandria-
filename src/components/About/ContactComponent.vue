<template>
  <section class="resume-section p-3 p-lg-5 d-flex align-items-center" id="contact">
    <div class="w-100">
      <h2 class="mb-2">Contact</h2>
      <form class="gform" method="POST" :data-email="About.email" :action="About.scriptlink">
        <div class="form-group">
          <label 
            class="subheading" 
            for="name">
            Name
          </label>
          <input 
            type="text" 
            class="form-control" 
            id="name"
            name="name"
            placeholder="Your name..." 
          />
        </div>
        <div class="form-group">
          <label 
            class="subheading" 
            for="contactinfo">
            Contact Info
          </label>
          <input 
            type="text" 
            class="form-control" 
            id="contactinfo"
            name="contactinfo"
            placeholder="name@example.com" 
          />
        </div>
        <div class="form-group">
          <label 
            class="subheading" 
            for="exampleInputEmail1"
            >Why are you here?</label>
          <div 
            v-for="(option, index) in About.options" 
            v-bind:key="'FormOption' + index" 
            class="form-check"
            >
            <input 
              class="form-check-input" 
              type="radio" 
              name="reason" 
              :id="'gridRadios' + index" 
              :value="option"
              v-bind:checked="index === ContactIndex"
              />
            <label class="form-check-label" :for="'gridRadios' + index">
              {{option}}
            </label>
          </div>
        </div>
        <div class="form-group">
          <label 
            class="subheading" 
            for="exampleFormControlTextarea1">
            Message (Optional)
          </label>
          <textarea 
            class="form-control" 
            id="exampleFormControlTextarea1" 
            rows="3" 
            name="message"
            placeholder="Send me a message..."></textarea>
        </div>
        <button type="submit" class="btn btn-xl">Submit</button>
        <div style="display:none" class="thankyou_message">
          <h3>
            Thanks for contacting me! I'll get back to you soon!
          </h3>
        </div>
      </form>
    </div>
  </section>
</template>

<script lang="ts">
import ContactComponent from './ContactComponent.vue';

export default {
  name: "ContactComponent",
  props: {
    About: Object,
    ContactIndex: Number
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

h2, h3 {
  color: white;
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

.form-check-label {
  font-size: 1.25rem;
}

.subheading {
  margin: 0;
}

.form-check-input {
  margin-top: 10px;;
}

.form-check, .form-check input, .form-check label {
  cursor: pointer;
}
</style>
