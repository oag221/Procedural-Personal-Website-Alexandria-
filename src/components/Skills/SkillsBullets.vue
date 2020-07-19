<template>
  <div class="bullets">
    <div v-for="(section, index) in Bullets" v-bind:key="'Bullet' + index">
      <div class="subheading mb-3">{{section.heading}}</div>
      <ul class="fa-ul mb-0">
        <li v-for="(bullet, bindex) in section.bullets" v-bind:key="index + '' + bindex">
          <i class="fa-li fa fa-check"></i>
          {{ bullet }}
        </li>
      </ul>
    </div>
  </div>
</template>

<script lang="ts">
export default {
  name: 'SkillsBullets',
  props: {
    Bullets: Array
  }
}
</script>

<style scoped lang="scss">
</style>