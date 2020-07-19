<template>
  <div class="social-icons mt-3" v-if="SocialMedia">
    <span v-if="SocialMedia.linkedin">
      <a :href="SocialMedia.linkedin" target="_blank" data-toggle="tooltip" data-placement="bottom" title="LinkedIn">
        <i class="fab fa-linkedin-in"></i>
      </a>
    </span>
    <span v-if="SocialMedia.facebook">
      <a :href="SocialMedia.facebook" target="_blank" data-toggle="tooltip" data-placement="bottom" title="Facebook">
        <i class="fab fa-facebook-f"></i>
      </a>
    </span>
    <span v-if="SocialMedia.github">
      <a :href="SocialMedia.github" target="_blank" data-toggle="tooltip" data-placement="bottom" title="Github">
        <i class="fab fa-github"></i>
      </a>
    </span>
    <span v-if="SocialMedia.twitter">
      <a :href="SocialMedia.twitter" target="_blank" data-toggle="tooltip" data-placement="bottom" title="Twitter">
       <i class="fab fa-twitter"></i>
      </a>
    </span>
  </div>
</template>

<script lang="ts">
export default {
  name: 'AboutSocialMedia',
  props: {
    SocialMedia: Object
  }
}
</script>

<style scoped lang="scss">
.social-icons span a {
  display: inline-block;
  height: 3.5rem;
  width: 3.5rem;
  background-color: #2196F3;
  color: #fff !important;
  border-radius: 50%;
  text-align: center;
  font-size: 1.5rem;
  line-height: 3.5rem;
  margin-right: 1rem;
  border: 1px solid #2196F3;
  transition: 0.15s ease-in-out;
}

.social-icons span {
  margin: 0 5px;
}

.social-icons span a:last-child {
  margin-right: 0;
}

.social-icons span a:hover {
  background-color: white;
  border-color: #2196F3;
}

.social-icons span a:hover i {
  color: #2196F3;
}
</style>