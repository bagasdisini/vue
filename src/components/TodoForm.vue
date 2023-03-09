<template>
  <form class="row g-3 mt-2 " @submit.prevent="addTodo">
    <div class="col-7 ">
      <input type="text" class="form-control" v-model="newTodo" placeholder="Input">
    </div>
    <div class="col-5">
      <button class="btn btn-primary mb-3">Add Todo</button>
    </div>
  </form>
  
</template>

<script>
export default {
  data() {
    return {
      newTodo: '',
    }
  },
  methods: {
    addTodo() {
      this.$emit('addTodo', this.newTodo);
      this.newTodo = '';
    }
  }
}
</script>