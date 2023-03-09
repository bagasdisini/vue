<template>
  <div>
    <h1>CRUD Todo List with Vite VueJS 3</h1>
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
