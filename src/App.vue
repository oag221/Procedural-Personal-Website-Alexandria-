<template>
  <div class="main-wrapper">
    <AsideComponent/>

    <div class="container-fluid p-0">
      <AboutComponent/>
      <hr class="m-0" />
      <ExperienceComponent/>
      <hr class="m-0" />
      <EducationComponent/>
      <hr class="m-0" />
      <SkillsComponent/>
      <hr class="m-0" />
      <InterestsComponent/>
      <hr class="m-0" />
      <AwardsComponent/>
    </div>
  </div>
</template>

<script>
import AsideComponent from './components/AsideComponent'
import AboutComponent from './components/AboutComponent.vue'
import ExperienceComponent from './components/ExperienceComponent.vue'
import EducationComponent from './components/EducationComponent.vue'
import SkillsComponent from './components/SkillsComponent.vue'
import InterestsComponent from './components/InterestsComponent'
import AwardsComponent from './components/AwardsComponent'

export default {
  components: {
    AsideComponent,
    AboutComponent,
    ExperienceComponent,
    EducationComponent,
    SkillsComponent,
    InterestsComponent,
    AwardsComponent
  },
  data() {
    return {
      title: "My portfolio"
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
    })
  }
};
</script>

<style>
</style>
