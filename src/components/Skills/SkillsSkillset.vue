<template>
  <div>
    <div class="subheading">{{skillset.title}}</div>
    <ul class="list-inline dev-icons">
      <li v-for="(skill, idx) in skillset.list" class="list-inline-item" v-bind:key="skillset.title + 'Skill' + idx">
        <i v-bind:class="skill.icon" class="icon" data-toggle="tooltip" data-placement="bottom" v-bind:title="skill.title"></i>
      </li>
    </ul>
  </div>
</template>

<script lang="ts">
export default {
  name: "SkillsSkillset",
  props: {
    skillset: Object,
    index: Number
  }
};
</script>

<style scoped lang="scss">
.icon {
  cursor: pointer;
}
</style>
