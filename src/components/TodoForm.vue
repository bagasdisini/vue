<template>
  <form @submit.prevent="$emit('addTodo', newTodo)">
    <input type="text" v-model="newTodo" />
    <button>Add Todo</button>
  </form>
</template>

<script>
export default {
  data() {
    return {
      newTodo: '',
    }
  },
}
</script>