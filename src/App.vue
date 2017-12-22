<template>
  <div id='app'>
    <!--  pass data from main component to the ToDoList component using v-bind directive -->
    <!-- v-bind directive takes the todos argument and binds the element's todos attribuet to the value of the expression todos -->
    <to-do-list v-bind:todos='todos'></to-do-list>
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
  // provide data to the template
  data() {
    return {
      todos: [
        {
          title: 'wrap christmas presents',
          project: 'home',
          done: false,
        },
        {
          title: 'a little life by hanya yanagihara',
          project: 'read',
          done: false,
        },
        {
          title: 'learn SASS',
          project: 'learn',
          done: false,
        },
        {
          title: "finish vivi's website",
          project: 'vvsundays',
          done: false,
        },
      ],
    };
  },
};
</script>

<style>

</style>
