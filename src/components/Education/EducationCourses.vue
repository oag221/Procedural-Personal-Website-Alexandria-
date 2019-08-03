<template>
  <span class="courses">
    <h5 class="title">
      <span v-if="Courses.length === 1">Relevant Course:</span>
      <span v-if="Courses.length > 1">Relevant Courses:</span>
    </h5>
    <div class="accordion" id="accordionCourses">
      <div v-for="(courses, index) in Courses" v-bind:key="'Courses' + index" class="card">
        <div class="mb-0 card-header" :id="'heading' + index">
          <button 
              class="btn btn-link collapsed" 
              type="button" 
              data-toggle="collapse" 
              :data-target="'#collapse' + index" 
              aria-expanded="false" 
              :aria-controls="'collapse' + index"
            >
            <h5 class="card-title">{{courses.code}} - {{courses.title}}</h5>
          </button>
        </div>
        <div 
          :id="'collapse' + index" 
          class="collapse" 
          :aria-labelledby="'heading' + index" 
          data-parent="#accordionCourses"
        >
          <div class="card-body">
            {{courses.description}}
          </div>
        </div>
      </div>
    </div>
  </span>
</template>

<script lang="ts">
export default {
  name: "EducationCourses",
  props: {
    Courses: Array
  }
};
</script>

<style scoped lang="scss">
.card-header {
  padding: 0;
}

.course-wrapper .card {
  max-width: 15rem; 
  width: 15rem;
  height: 6rem;
  padding: 0rem;
}

.course-wrapper .card .card-body {
  padding: 0.5rem;
}

.card-title, .code {
  margin-bottom: 0;
}

.card-text {
  font-size: .75rem;
}

.btn.btn-link {
  text-decoration: none;
  width: 100%;
  text-align: left;
}

.accordion {
  max-width: 36rem;
}

.title {
  font-weight: 500;
}
</style>
