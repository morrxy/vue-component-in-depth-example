<template>
  <div>
    <my-component :message="message" v-slot:default="{ text }">
      {{ text }}
    </my-component>
  </div>
</template>

<script>
const myComponent = {
  props: ['message'],
  render: function(createElement) {
    // `<div><slot :text="message"></slot></div>`
    return createElement('div', [
      this.$scopedSlots.default({
        text: this.message
      })
    ]);
  }
};

export default {
  components: {
    'my-component': myComponent
  },
  data() {
    return {
      message: 'hello world!'
    };
  }
};
</script>
