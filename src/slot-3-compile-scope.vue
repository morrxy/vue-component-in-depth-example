<template>
  <div>
    <navigation-link url="/profile"> Logged in as {{ user.name }} </navigation-link>

    <br />

    <navigation-link url="/profile"> Clicking here will send you to: {{ url }} </navigation-link>
  </div>
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
  },
  data() {
    return {
      user: {
        name: 'yourName'
      }
    };
  }
};
</script>
