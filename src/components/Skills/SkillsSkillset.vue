<template>
  <div>
    <div class="subheading">{{skillset.title}}</div>
    <ul class="list-inline">
      <li v-on:click="toggleActivated(skill.index)" v-bind:class="{active: activeIndex === skill.index}" v-for="(skill, idx) in skillset.skills" class="list-inline-item" v-bind:key="skillset.title + 'Skill' + idx">
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
    activeIndex: Number
  },
  methods: {
    toggleActivated (index: number) {
      this.$emit('toggleActivated', index)
    }
  }
};
</script>

<style scoped lang="scss">
.icon {
  cursor: pointer;
  padding: .5rem;
}

ul li {
  font-size: 2rem;
  border-radius: .4rem;
  border: solid 1px transparent;
}

ul li.active {
  background-color: #2196F3;
  border: solid 1px #2196F3;
  transition: 0.15s ease-in-out;
}

ul li.active:hover {
  background-color: #ffffff;
}

ul li.active:hover > i {
  color: #2196F3;
}

ul li.active > i {
  color: #FFFFFF;
}
</style>
