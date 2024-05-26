<template>
  <div class="todo-list">
    <h1>PENGUMPULAN TUGAS</h1>
    <ul>
      <TodoItem
        v-for="task in tasks"
        :key="task.id"
        :task="task"
        @show-details="showDetails"
      />
    </ul>
    <slot name="details" :selected-task="selectedTask"></slot>
  </div>
</template>

<script>
import TodoItem from "./TodoItem.vue";

export default {
  name: "TodoList",
  components: { TodoItem },
  data() {
    return {
      tasks: [
        {
          id: 1,
          title: "Tugas 1",
          details:
            "Cyber security adalah tindakan perlindungan perangkat, jaringan, program dan data dari ancaman serangan siber serta akses ilegal. Dengan cyber security, risiko kehilangan saldo dan data pribadi pengguna dapat diminimalkan. ",
        },
        {
          id: 2,
          title: "Tugas 2",
          details:
            "Front-End Developer adalah seorang profesional dalam bidang teknologi informasi yang bertanggung jawab untuk mengembangkan dan memelihara bagian depan suatu website.Mereka memiliki pengetahuan mendalam tentang bahasa pemrograman seperti HTML, CSS, dan JavaScript, serta memiliki keahlian dalam desain web dan pengalaman pengguna.",
        },

        {
          id: 3,
          title: "Tugas 3",
          details:
            "DevOps merupakan singkatan dari dua kata yaitu Development dan Operation. Di mana kedua kata tersebut bermakna menggabungkan proses development/pengembangan dari sebuah sistem/aplikasi dengan operation/operasional. Seperti yang disebutkan sebelumnya, DevOps adalah sebuah prinsip developer untuk mengkoordinasikan antar tim yaitu tim development dengan tim operations dengan efektif dan efisien.",
        },
      ],
      selectedTask: null,
    };
  },
  methods: {
    showDetails(task) {
      this.selectedTask = task;
      this.$emit("task-selected", task); // Emit event ke parent ketika task dipilih
    },
  },
};
</script>

<style scoped>
.todo-list {
  color: black;
  max-width: 600px;
  margin: 0 auto;
  font-family: Arial, sans-serif;
}

ul {
  list-style: none;
  padding: 0;
}

h1 {
  text-align: center;
  color: #000000;
}
</style>
