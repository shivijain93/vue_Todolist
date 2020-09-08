<template>
  <div id="app">
    
    <todo-list></todo-list>
    <task-list></task-list>
  </div>
</template>

<script>

import TodoList from './components/TodoList'
import TaskList from './components/TaskList'

export default {
  name: 'App',
  components: {
   
    TodoList,
    TaskList
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
