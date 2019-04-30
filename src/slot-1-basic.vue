<template>
  <alert-box>Something bad happened.</alert-box>
</template>

<script>
const alertBox = {
  template: `
        <div class="demo-alert-box">
          <strong>Error!</strong>
          <slot></slot>
        </div>
      `
};

export default {
  components: {
    'alert-box': alertBox
  }
};
</script>
