<template>
  <input type="text" v-model="newTodoText" />
  <button v-on:click="addTodo">Añadir tarea</button>
  <hr>
  <ul>
      <div class="todo" v-for="todo in todos" :key="todo">
        <li>{{todo.text}}</li>
        <button v-on:click="deleteTodo(todo.id)">Eliminar tarea</button>
      </div>
      <div v-if="todos.length < 1">
          Añada una tarea para ver la lista.
      </div>
  </ul>
</template>

<script>
let nextTodoId = 1;

export default {
  name: 'TodoList',
  components: {

  },
  data() {
      return {
          todos: [
              {id: nextTodoId++, text: 'Todo 1'},
              {id: nextTodoId++, text: 'Todo 2'},
              {id: nextTodoId++, text: 'Todo 3'}
          ]
      }
  },
  methods: {
      addTodo: function() {
          if (this.newTodoText) {
          const trimmedText = this.newTodoText.trim()
			if (trimmedText) {
				this.todos.push({
                    id: nextTodoId++,
					text: trimmedText
				})
				this.newTodoText = ''
			}
          }
      },
      deleteTodo(idToRemove) {
        this.todos = this.todos.filter(todo => {
            return todo.id !== idToRemove
        })
      }
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
.todo {
    display: flex;
    justify-content: center;
    padding: 8px;
}
</style>
