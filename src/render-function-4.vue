<template>
  <div>
    <my-input :value="value" @input="handleInput" />
    {{ value }}
  </div>
</template>

<script>
const myComponent = {
  props: ['value'],
  render: function(createElement) {
    const vm = this;
    return createElement('input', {
      domProps: {
        value: vm.value
      },
      on: {
        input: function(event) {
          vm.$emit('input', event.target.value);
        }
      }
    });
  }
};

export default {
  components: {
    'my-input': myComponent
  },
  data() {
    return {
      value: 'initValue'
    };
  },
  methods: {
    handleInput(val) {
      this.value = val;
    }
  }
};
</script>
