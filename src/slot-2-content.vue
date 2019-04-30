<template>
  <navigation-link url="/profile">
    Your Profile
  </navigation-link>
</template>

<script>
const navigationLink = {
  props: ['url'],
  template: `
    <a v-bind:href="url" class="nav-link">
      <slot></slot>
    </a>
  `
};

export default {
  components: {
    'navigation-link': navigationLink
  }
};
</script>
