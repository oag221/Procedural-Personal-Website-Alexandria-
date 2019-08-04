<template>
  <span>
    <div class="card" style="width: 15rem;" data-toggle="modal" :data-target="'#Modal' + Interest.skill">
      <div class="darken">
        <div class="darken-overlay">
          <div class="card-img-overlay">
            <h5 class="card-title card-skill">{{Interest.skill}}</h5>
            <h6 class="card-title">{{Interest.role}}, {{Interest.organization}}</h6>
          </div>
        </div>
        <img v-bind:src="require(`../../assets/img/${Interest.image}`)" class="card-img-top img-square">
      </div>
    </div>
    <!-- Modal -->
    <div class="modal fade" :id="'Modal' + Interest.skill" tabindex="-1" role="dialog" aria-labelledby="exampleModalLabel" aria-hidden="true">
      <div class="modal-dialog" role="document">
        <div class="modal-content">
          <div class="modal-header">
              <div class="modal-title" id="exampleModalLabel">
                <h4>{{Interest.organization}}</h4>
                <div class="subheading">{{Interest.role}}</div>
              </div>
              <button type="button" class="close" data-dismiss="modal" aria-label="Close">
                <span aria-hidden="true">&times;</span>
              </button>
          </div>
          <div class="modal-body">
            <p v-for="(description, dindex) in Interest.description" v-bind:key="'D' + dindex">{{description}}</p>
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
  border: 0;
}

.card-title {
  color: #f5f5f5;
  opacity: 1;
  margin-bottom: .25rem;
  z-index: 1;
}

.card-title:hover {
  color: #ffffff;
}

div.darken {
  background-color: black;
  border-radius: .5rem;
}

div.darken img {
  opacity: .35;
  transition: 0.1s ease-in;
  border-radius: .5rem;
}

div.darken img:hover {
  opacity: .45;
}
</style>
