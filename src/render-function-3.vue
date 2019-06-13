<template>
  <div>
    <my-component :items="items1" />
    <my-component :items="items2" />
  </div>
</template>

<script>
const comp = {
  props: {
    items: {
      type: Array,
      required: true
    }
  },
  render: function(createElement) {
    if (this.items.length) {
      return createElement(
        'ul',
        this.items.map(function(item) {
          return createElement('li', item.name);
        })
      );
    } else {
      return createElement('p', 'No items found');
    }
  }
};

export default {
  components: {
    'my-component': comp
  },
  data() {
    return {
      items1: [
        {
          name: 'name1'
        },
        {
          name: 'name2'
        }
      ],
      items2: []
    };
  }
};
</script>
