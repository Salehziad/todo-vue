<template>
  <div class="container">
    <Header @showAdd="showAddTasks" title="Task Tracker" :showAddTask="showAddTask" />
    <div v-if="showAddTask">
      <AddTask @add-task="addtask" />
    </div>
    <Tasks
      @delete-task="deleteTask"
      @toggle-reminder="toogleReminder"
      :tasks="tasks"
    />
  </div>
</template>

<script>
import Header from "../components/Header";
import Tasks from "../components/Tasks";
import AddTask from "../components/AddTask";

export default {
  name: "Home",
  components: {
    Header,
    Tasks,
    AddTask,
  },
  data() {
    return {
      tasks: [],
      showAddTask: false,
    };
  },
  methods: {
    deleteTask(id) {
      if (confirm("Are you shure")) {
        this.tasks = this.tasks.filter((task) => task.id !== id);
      }
    },
    toogleReminder(id) {
      this.tasks = this.tasks.map((task) =>
        task.id === id ? { ...task, reminder: !task.reminder } : task
      );
    },
    addtask(task) {
      console.log(task);
      this.tasks = [...this.tasks, task];
    },
    showAddTasks(){
      console.log("gggg");
      this.showAddTask=!this.showAddTask
    }
  },
  created() {
    this.tasks = [
      {
        id: 1,
        text: "play",
        day: "march",
        reminder: true,
      },
      {
        id: 2,
        text: "study",
        day: "tomorrow",
        reminder: false,
      },
      {
        id: 3,
        text: "work",
        day: "now",
        reminder: true,
      },
      {
        id: 4,
        text: "ssssaaa",
        day: "ssssss",
        reminder: false,
      },
    ];
  },
};
</script>

<style scoped>
.container {
  max-width: 500px;
  margin: 30px auto;
  overflow: auto;
  min-height: 300px;
  border: 1px solid steelblue;
  padding: 30px;
  border-radius: 5px;
}
</style>
