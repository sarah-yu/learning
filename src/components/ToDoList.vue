<!--  ToDoList Component -->
<!--  each component consists a template, component class, and style section -->

<template>
  <div>
    <p>Complete: {{toDos.filter(toDo => {return toDo.done}).length}}</p>
    <p>Incomplete: {{toDos.filter(toDo => {return toDo.done === false}).length}}</p>

    <!-- pass data and methods to the ToDo component -->
    <to-do  v-for='(toDo, index) in toDos' v-bind:toDo='toDo' v-bind:index='index' :key='toDo.id' v-on:delete-toDo='deleteToDo'></to-do>
  </div>
</template>

<script type = 'text/javascript' >
import ToDo from './ToDo';

export default {
  // allow ToDoList component to take toDos as props
  props: ['toDos'],
  components: {
    ToDo,
  },
  methods: {
    // event handler for the toDo item emitted from ToDo component
    deleteToDo(toDo) {
      const toDoIndex = this.toDos.indexOf(toDo);
      this.toDos.splice(toDoIndex, 1);
    },
  },
};
</script>

<style>
</style>
