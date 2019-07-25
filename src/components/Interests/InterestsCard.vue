<template>
  <span>
    <div class="card" style="width: 18rem;" data-toggle="modal" :data-target="'#Modal' + Interest.skill">
      <img v-bind:src="require(`../../assets/img/${Interest.image}`)" class="card-img-top img-square">
      <div class="card-body">
        <p class="card-text">{{Interest.skill}}</p>
      </div>
    </div>
    <!-- Modal -->
    <div class="modal fade" :id="'Modal' + Interest.skill" tabindex="-1" role="dialog" aria-labelledby="exampleModalLabel" aria-hidden="true">
      <div class="modal-dialog" role="document">
        <div class="modal-content">
          <div class="modal-header">
            <div class="w-100">
              <h4 class="modal-title" id="exampleModalLabel">{{Interest.organization}}</h4>
              <button type="button" class="close" data-dismiss="modal" aria-label="Close">
                <span aria-hidden="true">&times;</span>
              </button>
            </div>
            <div class="subheading">{{Interest.role}}</div>

          </div>
          <div class="modal-body">
            {{Interest.description}}
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
  name: "InterestsComponent",
  props: {
    Interest: Object
  }
}
</script>

<style scoped lang="scss">
section.resume-section {
  min-height: 50vh;
}

.card {
  cursor: pointer;
}

.modal-content .modal-header {
  flex-direction: column;
}

.modal-content .modal-header div button {
  margin-left: 0;
  align-self: end;
}

.modal-content .modal-header div h4 {
  display: inline-block;
}
</style>
