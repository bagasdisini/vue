<template>
  <li :class="{ completed }" class="list-group-item d-flex justify-content-between border-0 mb-2 rounded"
      :style="computedStyles" @click="toggleComplete">
    <div class="d-flex align-items-center">
      <input class="form-check-input me-2" type="checkbox" :checked="completed" aria-label="..." />
      <span class="fs-6">{{ todo.text }}</span>
    </div>
    <a @click="deleteTodo" data-mdb-toggle="tooltip" title="Remove item">
      <i class="fas fa-times" :style="{ color: completed ? '#fff' : '#0d6efd' }"></i>
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
  computed: {
    computedStyles() {
      return {
        backgroundColor: this.completed ? '#0d6efd' : '#f4f6f7',
        boxShadow: this.completed ? 'rgba(13, 110, 253, 0.25) 0px 8px 24px' : '',
        color: this.completed ? '#fff' : '',
      };
    },
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