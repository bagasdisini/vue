<template>
  <li :class="{ completed }" class="list-group-item d-flex justify-content-between border-0 mb-2 rounded"
    style="background-color: #f4f6f7;">
    <div class="d-flex align-items-center">
      <input @click="toggleComplete" class="form-check-input me-2" type="checkbox" value="" aria-label="..." />
      <span>{{ todo.text }}</span>
    </div>
    <a @click="deleteTodo" href="#!" data-mdb-toggle="tooltip" title="Remove item">
      <i class="fas fa-times text-primary"></i>
    </a>
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
