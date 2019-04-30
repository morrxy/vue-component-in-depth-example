<template>
  <div>
    <submit-button />
    <submit-button>Save</submit-button>
  </div>
</template>

<script>
const button = {
  template: `
    <button type="submit">
      <slot>Submit</slot>
    </button>
  `
};

export default {
  components: {
    'submit-button': button
  }
};
</script>
