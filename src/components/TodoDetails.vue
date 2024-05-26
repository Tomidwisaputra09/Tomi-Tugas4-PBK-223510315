<template>
  <div v-if="task" class="todo-details">
    <h2>{{ task.title }}</h2>
    <p>{{ task.details }}</p>
  </div>
</template>

<script>
export default {
  name: "TodoDetails",
  props: {
    task: Object,
  },
};
</script>

<style scoped>
.todo-details {
  color: black;
  padding: 20px;
  border: 1px solid #42b983;
  margin-top: 20px;
  background-color: rgb(255, 253, 193);
}

h2 {
  margin-top: 0;
  color: #ff0000;
}
</style>
