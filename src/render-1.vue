<template>
  <div>
    <anchorded-heading :level="1">Hello world!</anchorded-heading>
    <anchorded-heading :level="2">Hello world!</anchorded-heading>
    <anchorded-heading :level="3">Hello world!</anchorded-heading>
  </div>
</template>

<script>
const heading = {
  props: {
    level: {
      type: Number,
      required: true
    }
  },
  render: function(createElement) {
    return createElement('h' + this.level, this.$slots.default);
  }
};

export default {
  components: {
    'anchorded-heading': heading
  }
};
</script>
