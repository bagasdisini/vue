<template>
  <section>
    <div class="container py-5 h-100">
      <div class="row d-flex justify-content-center align-items-center">
        <div class="col col-xl-5">
          <div class="card" style="border-radius: 15px; box-shadow: 0px 0px 10px -5px rgba(0,0,0,0.75);">
            <div class="card-body p-5">
              <h2 class="mb-3">Todo List</h2>
              <todo-item v-for="(todo, index) in todos" :key="index" :todo="todo" @toggleComplete="toggleComplete(index)"
                @deleteTodo="deleteTodo(index)"></todo-item>
              <todo-form @addTodo="addTodo"></todo-form>
            </div>
          </div>
          <footer class="d-flex justify-content-center align-items-center mt-5 pt-5">
            <p class="text-muted">Made with ❤️ by Kelompok 3</p>
          </footer>
        </div>
      </div>
    </div>
  </section>

</template>

<script>
import TodoItem from './TodoItem.vue'
import TodoForm from './TodoForm.vue'

export default {
  components: {
    TodoItem,
    TodoForm,
  },
  props: {
    todos: {
      type: Array,
      required: true,
    },
  },
  methods: {
    toggleComplete(index) {
      this.$emit('toggleComplete', index)
    },
    deleteTodo(index) {
      this.$emit('deleteTodo', index)
    },
    addTodo(newTodo) {
      this.$emit('addTodo', newTodo)
    },
  },
}
</script>