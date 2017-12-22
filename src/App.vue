<template>
  <div id="app">
    <to-do-list></to-do-list>
  </div>
</template>

<script>
// import the components you want to use
import ToDoList from './components/ToDoList';

export default {
  name: 'app',
  // reference the components you want to use in the components property
  components: {
    ToDoList,
  },

};
</script>

<style>

</style>
