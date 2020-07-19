<template>
  <section class="resume-section p-3 p-lg-5 d-flex align-items-center" id="about">
    <div class="w-100">
      <h1 class="mb-0 name">
        <span class="d-lg-none image-name">
          <img
            class="img-fluid img-profile rounded-circle mx-auto mb-2 profile-pic"
            src="../../assets/img/profile.jpg"
            alt="profile pic"
          />
        </span>
        <span class="d-sm-none small-name">
          {{About.firstName}}
          <span class="text-primary">{{About.lastName}}</span>
        </span>
        <span class="d-sm-block d-none">
          {{About.firstName}}
          <span class="text-primary">{{About.lastName}}</span>
        </span>
      </h1>
      <AboutContact :About="About" />
      <p class="lead mb-3" v-for="(paragraph, index) in About.bio" v-bind:key="'Bio' + index">
        {{paragraph}}
      </p>
      <AboutSocialMedia :SocialMedia="About.socialmedia" v-if="About.socialmedia" />
      <div class="resume mt-4">
        <button class="btn btn-primary btn-lg" v-on:click="resume()">
          <i class="fas fa-file-pdf"></i>
          Resume
        </button>
      </div>
    </div>
  </section>
</template>

<script lang="ts">
import AboutSocialMedia from './AboutSocialMedia.vue'
import AboutContact from './AboutContact.vue'

export default {
  name: 'AboutComponent',
  props: {
    About: Object
  },
  components: {
    AboutSocialMedia,
    AboutContact
  },
  methods: {
    resume () {
      window.open('/' + this.About.resume)
    }
  }
}
</script>

<style scoped lang="scss">
section.resume-section {
  min-height: 80vh;
}

img.img-fluid.img-profile.rounded-circle.profile-pic {
  width: 10rem;
  height: 10rem;
  justify-self: center;
}

.image-name {
  display: flex;
  justify-content: flex-start;
}

.small-name {
  font-size: 5rem;
}
</style>
