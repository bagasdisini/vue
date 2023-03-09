<template>
  <div>
    <nav class="navbar navbar-light bg-light ">
      <div class="container-fluid justify-content-center align-items-center">
        <a class="navbar-brand " href="#">
          <h1>CRUD Todo List with Vite VueJS 3</h1>
        </a>
      </div>
    </nav>
    
    <todo-list :todos="todos" @toggleComplete="toggleComplete" @deleteTodo="deleteTodo" @addTodo="addTodo"></todo-list>
  </div>
</template>

<script>
import TodoList from './components/TodoList.vue'
export default {
  components: {
    TodoList,
  },
  data() {
    return {
      todos: [],
    }
  },
  methods: {
    toggleComplete(index) {
      this.todos[index].completed = !this.todos[index].completed
    },
    deleteTodo(index) {
      this.todos.splice(index, 1)
    },
    addTodo(newTodo) {
      if (newTodo.trim() !== '') {
        this.todos.push({ text: newTodo, completed: false })
      }
    },
  },
}
</script>

<style>
.completed {
  text-decoration: line-through;
}
</style>
