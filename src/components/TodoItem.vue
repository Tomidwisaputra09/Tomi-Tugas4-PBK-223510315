<template>
  <button @click="handleClick" class="todo-item">
    {{ task.title }}
  </button>
</template>

<script>
export default {
  name: "TodoItem",
  props: {
    task: Object,
  },
  methods: {
    handleClick() {
      this.$emit("show-details", this.task);
    },
  },
};
</script>

<style scoped>
.todo-item {
  display: block;
  width: 100%;
  padding: 10px;
  margin-bottom: 5px;
  border: none;
  background-color: #42b983;
  color: white;
  text-align: left;
  cursor: pointer;
}

.todo-item:hover {
  background-color: #3c8d75;
}
</style>
