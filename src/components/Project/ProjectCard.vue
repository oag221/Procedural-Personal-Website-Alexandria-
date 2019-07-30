<template>
  <span class="projects-wrapper">
    <div class="card" data-toggle="modal" :data-target="'#Modal' + project.title">
      <div class="darken">
        <img v-bind:src="require(`../../assets/img/${project.image}`)" class="card-img-top img-square">
      </div>
      <div class="card-body">
        <h3 class="card-title">{{project.title}}</h3>
        <div class="subheading">{{project.subheading}}</div>
        <a target="_blank" href="https://www.preff.menu" class="btn btn-primary">Go somewhere</a>
      </div>
    </div>
    <!-- Modal -->
    <div class="modal fade" :id="'Modal' + project.title" tabindex="-1" role="dialog" aria-labelledby="exampleModalLabel" aria-hidden="true">
        <div class="modal-dialog" role="document">
          <div class="modal-content">
            <div class="modal-header">
              <h3 class="modal-title" id="exampleModalLabel">{{project.title}}</h3>
              <button type="button" class="close" data-dismiss="modal" aria-label="Close">
                <span aria-hidden="true">&times;</span>
              </button>
            </div>
            <div class="modal-body">
              {{project.description}}
            </div>
            <div class="modal-footer">
              <button type="button" class="btn btn-secondary" data-dismiss="modal">Close</button>
            </div>
          </div>
        </div>
    </div>
  </span>
</template>

<script lang="ts">
export default {
  name: "ProjectCard",
  props: {
    project: Object
  }
};
</script>

<style scoped lang="scss">
.projects-wrapper {
  display: flex;
  flex-direction: column;
}

.card {
  max-width: 80%;
  align-self: center;
  cursor: pointer;
}
</style>
