<template>
  <div id="app">
    <TodoList @task-selected="handleTaskSelected">
      <template #details="{ selectedTask }">
        <TodoDetails :task="selectedTask" />
      </template>
    </TodoList>
    <div v-if="selectedTask" class="selected-task-details">
      <h2>Detail Tugas Terpilih</h2>
      <p>{{ selectedTask.title }}</p>
      <p>{{ selectedTask.details }}</p>
    </div>
  </div>
</template>

<script>
import TodoList from "./components/TodoList.vue";
import TodoDetails from "./components/TodoDetails.vue";

export default {
  name: "App",
  components: { TodoList, TodoDetails },
  data() {
    return {
      selectedTask: null,
    };
  },
  methods: {
    handleTaskSelected(task) {
      this.selectedTask = task;
    },
  },
};
</script>

<style>
body {
  font-family: Arial, sans-serif;
  margin: 0;
  padding: 0;
  background-color: #b3d8e3;
}

#app {
  max-width: 800px;
  margin: 0 auto;
  padding: 20px;
}

.selected-task-details {
  padding: 20px;
  border: 1px solid #42b983;
  margin-top: 20px;
  background-color: #f0f0f0;
  color: black;
  background-color: rgb(255, 253, 193);
}

h2 {
  margin-top: 0;
  color: #ff0000;
}
</style>
