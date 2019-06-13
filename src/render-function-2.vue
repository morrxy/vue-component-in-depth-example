<template>
  <div>
    <anchorded-heading :level="1">Hello world!</anchorded-heading>
    <anchorded-heading :level="2">Hello world!</anchorded-heading>
    <anchorded-heading :level="3">Hello world!</anchorded-heading>
  </div>
</template>

<script>
function getChildrenTextContent(children) {
  return children
    .map(function(node) {
      return node.children ? getChildrenTextContent(node.children) : node.text;
    })
    .join('');
}

const heading = {
  props: {
    level: {
      type: Number,
      required: true
    }
  },
  render: function(createElement) {
    const headingId = getChildrenTextContent(this.$slots.default)
      .toLowerCase()
      .replace(/\W+/g, '-')
      .replace(/(^-|-$)/g, '');

    return createElement('h' + this.level, [
      createElement(
        'a',
        {
          attrs: {
            name: headingId,
            href: '#' + headingId
          }
        },
        this.$slots.default
      )
    ]);
  }
};

export default {
  components: {
    'anchorded-heading': heading
  }
};
</script>
