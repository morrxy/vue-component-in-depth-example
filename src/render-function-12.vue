<script>
import myButton from './render-function-12-button';

export default {
  components: {
    'my-button': myButton
  },

  render(h) {
    return h(
      'my-button',
      {
        attrs: {
          id: 'myButton',
          class: 'myclass',
          style: {
            color: 'orange'
          }
        },
        on: {
          click: function() {
            alert('clicked');
          }
        }
      },
      'my button'
    );
  }
};
</script>
