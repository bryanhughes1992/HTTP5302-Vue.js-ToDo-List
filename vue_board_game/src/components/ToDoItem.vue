<template>
  <div>
    <input type="checkbox" id="todo-item" v-bind:checked="isDone" />
    <label v-bind:for="id">{{label}}</label>
  </div>
</template>

<script>
  // Allows for dynamic id assignment
  import uniqueId from 'lodash.uniqueid';

  export default {
    props: {
      label: {
        required: true,
        type: String
      },
      done: {
        default: false,
        type: Boolean
      },
      id: {
        required: true,
        type: String
      }
    },
    data() {
      return {
        isDone: this.done,
        id: uniqueId('todo-')
      };
    }
  };
</script>