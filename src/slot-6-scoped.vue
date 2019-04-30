<template>
  <div>
    <current-user></current-user>

    <br />

    <current-user>
      <template v-slot:default="slotProp">
        {{ slotProp.user.firstName }}
      </template>
    </current-user>

    <br />

    <current-user v-slot:default="slotProp">
      {{ slotProp.user.firstName }}
    </current-user>

    <br />

    <current-user v-slot:default="{ user }">
      {{ user.firstName }}
    </current-user>
  </div>
</template>

<script>
const myComponent = {
  data() {
    return {
      user: {
        firstName: 'HH',
        lastName: 'JJ'
      }
    };
  },

  template: `
    <span>
      <slot :user="user">
        {{ user.lastName }}
      </slot>
    </span>
  `
};

export default {
  components: {
    'current-user': myComponent
  }
};
</script>
