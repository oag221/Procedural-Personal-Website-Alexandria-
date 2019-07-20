<template>
  <section class="resume-section p-3 p-lg-5 d-flex align-items-center" id="education">
    <div class="w-100">
      <h2 class="mb-5">Education</h2>

      <div v-for="(education, index) in EducationList" v-bind:key="'EducationList' + index">
        <div class="resume-item d-flex flex-column flex-md-row justify-content-between mb-5">
          <div class="resume-content">
            <div class="mb-0 school-name-date">
              <span class="school-name">
                {{education.name}}
              </span>
              <span class="resume-date text-md-right school-date">
                <span class="text-primary">{{education.startDate}} - {{education.endDate}}</span>
              </span>
            </div>
            <div class="subheading mb-3" v-if="education.degree">{{education.degree}}</div>
            <div v-if="education.major">
              <span v-if="education.major.length === 1">Major: </span>
              <span v-if="education.major.length > 1">Majors: </span>
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
            <div v-if="education.description">
              {{education.description}}
            </div>
          </div>
        </div>
        <hr v-if="index !== EducationList.length - 1"/>
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
section.resume-section {
  min-height: 50vh;
}

.resume-content {
  width: 100%;
}

.school-name-date {
  display: flex;
  justify-content: space-between;
}

.school-name {
  font-size: 2rem;
  font-weight: bold;
}

.school-date {
  font-size: 1.5rem;
}

</style>
