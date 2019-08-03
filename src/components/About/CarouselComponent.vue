<template>
  <div id="carouselExampleFade" class="carousel slide carousel-fade" data-ride="carousel">
    <div class="carousel-inner">
      <div v-for="(img, index) in About.carousel" v-bind:key="'Carousel' + index" class="carousel-item active">
        <img v-bind:src="require(`../../assets/img/${img.image}`)" class="d-block w-100" :alt="img.alt">
        <div class="carousel-caption d-none d-md-block">
          <h5>{{img.title}}</h5>
          <p>{{img.description}}</p>
        </div>
      </div>
    </div>
    <a class="carousel-control-prev" href="#carouselExampleFade" role="button" data-slide="prev">
      <span class="carousel-control-prev-icon" aria-hidden="true"></span>
      <span class="sr-only">Previous</span>
    </a>
    <a class="carousel-control-next" href="#carouselExampleFade" role="button" data-slide="next">
      <span class="carousel-control-next-icon" aria-hidden="true"></span>
      <span class="sr-only">Next</span>
    </a>
  </div>
</template>

<script lang="ts">
export default {
  name: "CarouselComponent",
  props: {
    About: Object
  }
};
</script>

<style scoped lang="scss">
.carousel {
  max-width: 60%;
  padding: 2rem;
  margin: auto;
}
</style>