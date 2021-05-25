<template>
  <h1>Todo List App</h1>
  <TodoList />
</template>

<script>
import TodoList from '../src/components/TodoList'

export default {
  name: 'TodoApp',
  components: {
    TodoList
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
