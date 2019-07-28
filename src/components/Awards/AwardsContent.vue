<template>
  <li class="main">
    <i class="fa-li fa fa-trophy"></i>
    <div class="header">
      <span><h3>{{Award.title}}</h3></span>
      <span class="text-primary award-date">{{Award.date}}</span>
    </div>
    <ul class="body" v-if="Award.bullets">
      <li v-for="(bullet, index) in Award.bullets" v-bind:key="'AwardBullet' + index">
        {{bullet}}
      </li>
    </ul>
  </li>
</template>

<script lang="ts">
export default {
  name: "AwardsComponent",
  props: {
    Award: Object
  }
}
</script>

<style scoped lang="scss">
.header {
  display: flex;
  justify-content: space-between;
}

span.award-date {
  font-size: 1.5rem;
}

i.fa-li.fa.fa-trophy {
  font-size: 1.5rem;
}

li.main {
  padding-top: 1rem;
  padding-bottom: 1rem;
}
</style>
