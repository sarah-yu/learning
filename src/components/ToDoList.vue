<!--  ToDoList Component -->
<!--  each component consists a template, component class, and style section -->

<template>
  <div>
    <p>Complete: {{todos.filter(todo => {return todo.done}).length}}</p>
    <p>Incomplete: {{todos.filter(todo => {return todo.done === false}).length}}</p>


  </div>
</template>

<script type = "text/javascript" >
export default {
  // allow ToDoList component to take todos as props
  props: ['todos'],
};
</script>

<style>
</style>
