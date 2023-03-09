<template>
  <li :class="{ completed }">
    <span @click="toggleComplete">{{ todo.text }}</span>
    <button @click="deleteTodo">X</button>
  </li>
</template>

<script>
export default {
  props: {
    todo: {
      type: Object,
      required: true,
    },
  },
  data() {
    return {
      completed: this.todo.completed,
    }
  },
  methods: {
    toggleComplete() {
      this.completed = !this.completed
      this.$emit('toggleComplete')
    },
    deleteTodo() {
      this.$emit('deleteTodo')
    },
  },
}
</script>
