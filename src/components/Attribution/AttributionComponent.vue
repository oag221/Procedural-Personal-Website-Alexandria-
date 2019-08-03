<template>
  <div class="bar">
    <p>
      Template Created from: 
      <a :href="Attribution.templatelink">
        {{Attribution.template}}
      </a>
    </p>
    <p>
      Design Inspired from: 
      <a :href="Attribution.inspirationlink">
        {{Attribution.inspiration}}
      </a>
    </p>
  </div>
</template>

<script lang="ts">
export default {
  name: "Attribution",
  props: {
    Attribution: Object
  }
};
</script>

<style scoped lang="scss">
.bar {
  background-color: #0069c0;
  padding: 0.5rem 1rem;
}

a {
  color: #f0f0f0;
}

p, a:hover {
  color: white;
  font-size: 0.75rem;
}

p {
  margin-bottom: 0;
}
</style>