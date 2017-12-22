<!--  ToDoList Component -->
<!--  each component consists a template, component class, and style section -->

<template>
  <div>
    <p>Complete: {{todos.filter(todo => {return todo.done}).length}}</p>
    <p>Incomplete: {{todos.filter(todo => {return todo.done === false}).length}}</p>

    <!-- pass data and methods to the ToDo component -->
    <to-do  v-for='(todo, index) in todos' v-bind:todo='todo' v-bind:index='index' :key='todo.id' v-on:delete-todo='deleteTodo'></to-do>
  </div>
</template>

<script type = 'text/javascript' >
import ToDo from './ToDo';

export default {
  // allow ToDoList component to take todos as props
  props: ['todos'],
  components: {
    ToDo,
  },
  methods: {
    // event handler for the todo item emitted from ToDo component
    deleteTodo(todo) {
      const todoIndex = this.todos.indexOf(todo);
      this.todos.splice(todoIndex, 1);
    },
  },
};
</script>

<style>
</style>
