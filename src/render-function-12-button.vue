<template functional>
  <button class="btn btn-primary" v-bind="data.attrs" v-on="listeners">
    <slot />
  </button>
</template>
