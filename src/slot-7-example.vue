<template>
  <div>
    <todo-list v-bind:todos="todos">
      <template v-slot:todo="{ todo }">
        <span v-if="todo.isComplete">✓</span>
        {{ todo.text }}
      </template>
    </todo-list>

    <br />

    <todo-list v-bind:todos="filteredTodos">
      <template v-slot:todo="{ todo }">
        <span v-if="todo.isComplete">✓</span>
        {{ todo.text }}
      </template>
    </todo-list>
  </div>
</template>

<script>
const myComponent = {
  props: {
    todos: {
      type: Array,
      required: true
    }
  },

  template: `
    <ul>
      <li
        v-for="todo in todos"
        v-bind:key="todo.id"
      >
        <slot name="todo" v-bind:todo="todo">
          {{ todo.text }}
        </slot>
      </li>
    </ul>
  `
};

export default {
  components: {
    'todo-list': myComponent
  },

  data() {
    return {
      todos: [
        {
          id: 1,
          text: 'do work 1',
          isComplete: true
        },
        {
          id: 2,
          text: 'do work 2',
          isComplete: false
        },
        {
          id: 3,
          text: 'do work 3',
          isComplete: false
        }
      ]
    };
  },

  computed: {
    filteredTodos() {
      return this.todos.filter(item => item.isComplete === true);
    }
  }
};
</script>
