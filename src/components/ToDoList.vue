<!--  ToDoList Component -->
<!--  each component consists a template, component class, and style section -->

<template>
  <div>
    <p>Complete: {{todos.filter(todo => {return todo.done}).length}}</p>
    <p>Incomplete: {{todos.filter(todo => {return todo.done === false}).length}}</p>

    <div class='ui centered card' v-for='todo in todos'>
      <div class='content'>
        <div class='header'>
          {{todo.title}}
        </div>

        <div class="meta">
          {{todo.project}}
        </div>

        <div class="extra content">
          <span class='right floated edit icon'>
            <i class='edit icon'></i>
          </span>
        </div>
      </div><!-- .content -->

      <div class='ui bottom attached green basic button' v-show="todo.done">
        Completed
      </div>
      <div class='ui bottom attached red basic button' v-show="!todo.done">
        Complete
      </div>
    </div>
  </div>
</template>

<script type = 'text/javascript' >
export default {
  // allow ToDoList component to take todos as props
  props: ['todos'],
};
</script>

<style>
</style>
