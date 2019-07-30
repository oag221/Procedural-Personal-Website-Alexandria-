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
}

ul li.active, ul li.active:hover {
  background-color: #2196F3;
  transition: 0.3s ease-out;
  border-radius: .4rem;
}

ul li.active > i, ul li.active > i:hover {
  color: #FFFFFF;
}
</style>
