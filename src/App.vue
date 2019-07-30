<template>
  <div class="main-wrapper">
    <AsideComponent :About="config.about" />

    <div class="container-fluid">
      <AboutComponent v-bind:About="config.about" />
      <hr class="m-0" />
      <ExperienceComponent v-bind:ExperienceList="config.experience" />
      <hr class="m-0" />
      <EducationComponent v-bind:EducationList="config.education" />
      <hr class="m-0" />
      <SkillsComponent v-bind:Skills="config.skills" />
      <hr class="m-0" />
      <InterestsComponent v-bind:Interests="config.personal" />
      <hr class="m-0" />
      <ProjectComponent v-bind:Projects="config.projects" />
      <hr class="m-0" />
      <AwardsComponent v-bind:Awards="config.awards" />
    </div>
  </div>
</template>

<script lang="ts">
import config from '../config/config.json'

import AsideComponent from './components/Aside/AsideComponent.vue';
import AboutComponent from './components/About/AboutComponent.vue';
import ExperienceComponent from './components/Experience/ExperienceComponent.vue';
import EducationComponent from './components/Education/EducationComponent.vue';
import SkillsComponent from './components/Skills/SkillsComponent.vue';
import InterestsComponent from './components/Interests/InterestsComponent.vue';
import ProjectComponent from './components/Project/ProjectComponent.vue';
import AwardsComponent from './components/Awards/AwardsComponent.vue';

export default {
  components: {
    AsideComponent,
    AboutComponent,
    ExperienceComponent,
    EducationComponent,
    SkillsComponent,
    InterestsComponent,
    ProjectComponent,
    AwardsComponent
  },
  data() {
    return {
      config: config
    };
  },
  mounted() {
    const $ = this.jquery;
    this.$nextTick(() => {
      // our custom jQuery code goes here
      $('a.js-scroll-trigger[href*="#"]:not([href="#"])').click(function () {
        if (location.pathname.replace(/^\//, '') === this.pathname.replace(/^\//, '') && location.hostname === this.hostname) {
          var target = $(this.hash)
          target = target.length ? target : $('[name=' + this.hash.slice(1) + ']')
          if (target.length) {
            $('html, body').animate({
              scrollTop: (target.offset().top)
            }, 1000, 'easeInOutExpo')
            return false
          }
        }
      })
      // Closes responsive menu when a scroll trigger link is clicked
      $('.js-scroll-trigger').click(function () {
        $('.navbar-collapse').collapse('hide')
      })
      // Activate scrollspy to add active class to navbar items on scroll
      $('body').scrollspy({
        target: '#sideNav'
      })
      $('[data-toggle="tooltip"]').tooltip()
    })
  }
};
</script>

<style scoped>
.container-fluid {
  padding: 0 0 5rem 0;
}
</style>
