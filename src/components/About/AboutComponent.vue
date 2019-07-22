<template>
  <section class="resume-section p-3 p-lg-5 d-flex align-items-center" id="about">
    <div class="w-100">
      <h1 class="mb-0">
        {{About.firstName}}
        <span class="text-primary">{{About.lastName}}</span>
      </h1>
      <div class="subheading mb-5">
        {{About.address.streetAddress}} · 
        {{About.address.city}}, {{About.address.state}} {{About.address.zip}} · 
        {{About.phone}} ·
        <a :href="'mailto:' + About.email" target="_blank">
          {{About.email}}
        </a>
      </div>
      <p class="lead mb-5">
        {{About.bio}}
      </p>
      <div class="social-icons" v-if="About.socialmedia">
        <span v-if="About.socialmedia.linkedin">
          <a :href="About.socialmedia.linkedin" target="_blank" data-toggle="tooltip" data-placement="bottom" title="LinkedIn">
            <i class="fab fa-linkedin-in"></i>
          </a>
        </span>
        <span v-if="About.socialmedia.facebook">
          <a :href="About.socialmedia.facebook" target="_blank" data-toggle="tooltip" data-placement="bottom" title="Facebook">
            <i class="fab fa-facebook-f"></i>
          </a>
        </span>
        <span v-if="About.socialmedia.github">
          <a :href="About.socialmedia.github" target="_blank" data-toggle="tooltip" data-placement="bottom" title="Github">
            <i class="fab fa-github"></i>
          </a>
        </span>
        <span v-if="About.socialmedia.twitter">
          <a :href="About.socialmedia.twitter" target="_blank" data-toggle="tooltip" data-placement="bottom" title="Twitter">
            <i class="fab fa-twitter"></i>
          </a>
        </span>
      </div>
      <div class="resume mt-4">
        <a class="btn btn-primary btn-lg" :href="pdf" target="_blank">
          <i class="fas fa-file-pdf"></i>
          Resume
        </a>
      </div>
    </div>
  </section>
</template>

<script lang="ts">

export default {
  name: "AboutComponent",
  props: {
    About: Object
  },
  data: () => {
    return {
      pdf: "https://www.williamperacchio.com/resume.pdf"
    }
  }
}
</script>

<style scoped lang="scss">
section.resume-section {
  min-height: 80vh;
}

</style>
