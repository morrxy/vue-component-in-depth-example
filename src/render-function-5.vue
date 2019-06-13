<template>
  <div>
    <my-component>hello world!</my-component>
  </div>
</template>

<script>
const myComponent = {
  render: function(createElement) {
    // `<div><slot></slot></div>`
    return createElement('div', this.$slots.default);
  }
};

export default {
  components: {
    'my-component': myComponent
  }
};
</script>
