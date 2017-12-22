<!--  ToDoList Component -->
<!--  each component consists a template, component class, and style section -->

<template>
  <div>
    <p>Complete: {{todos.filter(todo => {return todo.done}).length}}</p>
    <p>Incomplete: {{todos.filter(todo => {return todo.done === false}).length}}</p>

    <!-- pass data to the ToDo component -->
    <to-do  v-for='todo in todos' v-bind:todo='todo' :key='todo.id'></to-do>
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
};
</script>

<style>
</style>
