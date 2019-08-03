<template>
  <div>
    <div class="subheading mb-5 d-md-none">
      <div>{{About.address.city}}, {{About.address.state}} {{About.address.zip}}</div> 
      <div><a :href="'tel:' + About.formattedPhone">{{About.phone}}</a></div>
      <div><a :href="'mailto:' + About.email" target="_blank">{{About.email}}</a></div>
    </div>
    <div class="subheading mb-5 d-none d-md-block">
      {{About.address.city}}, {{About.address.state}} {{About.address.zip}} · 
      <a :href="'tel:' + About.formattedPhone">{{About.phone}}</a> ·
      <a :href="'mailto:' + About.email" target="_blank">{{About.email}}</a>
    </div>
  </div>
</template>

<script lang="ts">
export default {
  name: "AboutContact",
  props: {
    About: Object
  }
};
</script>

<style scoped lang="scss">
</style>