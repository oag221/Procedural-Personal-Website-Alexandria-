<template>
  <section class="resume-section p-3 p-lg-5 d-flex align-items-center" id="education">
    <div class="w-100">
      <h2 class="mb-5">Education</h2>

      <div v-for="(education, index) in EducationList" v-bind:key="index">
        <div class="resume-item d-flex flex-column flex-md-row justify-content-between mb-5">
          <div class="resume-content">
            <h3 class="mb-0">{{education.name}}</h3>
            <div class="subheading mb-3">{{education.degree}}</div>
            <div v-if="education.major">
              <span v-if="education.major.length === 1">Minor: </span>
              <span v-if="education.major.length > 1">Minors: </span>
              <span v-for="(major, majorIndex) in education.major" v-bind:key="education.name + 'Major' + major">
                {{major}}<span v-if="majorIndex !== education.major.length - 1">,
                  <span v-if="majorIndex === education.major.length - 2 && education.major.length > 2">
                    &amp;
                  </span>
                </span>
              </span>
            </div>
            <div v-if="education.minor">
              <span v-if="education.minor.length === 1">Minor: </span>
              <span v-if="education.minor.length > 1">Minors: </span>
              <span v-for="(minor, minorIndex) in education.minor" v-bind:key="education.name + 'Minor' + minor">
                {{minor}}<span v-if="minorIndex !== education.minor.length - 1">,
                  <span v-if="minorIndex === education.minor.length - 2 && education.minor.length > 2">
                    &amp;
                  </span>
                </span>
              </span>
            </div>
            <div v-if="education.gpa">
              <div v-if="education.gpa.cumulative">
                Cumulative GPA: {{education.gpa.cumulative}} / {{education.gpa.scale}}
              </div>
              <div v-if="education.gpa.major">
                Major GPA: {{education.gpa.major}} / {{education.gpa.scale}}
              </div>
            </div>
          </div>
          <div class="resume-date text-md-right">
            <span class="text-primary">{{education.startDate}} - {{education.endDate}}</span>
          </div>
        </div>
      </div>
      

    </div>
  </section>
</template>

<script lang="ts">
import { Component, Prop, Vue } from "vue-property-decorator";

@Component
export default class EducationComponent extends Vue {
  @Prop(Array) readonly EducationList: object[] | undefined;
}
</script>

<style scoped lang="scss">
</style>
