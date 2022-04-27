<template>
  <TaskHeader />
  <TaskForm @btn-click="addTask" />
  <TaskList :tasks="tasks" @span-click="deleteTask" />
</template>

<script>
import TaskHeader from "./components/TaskHeader.vue";
import TaskForm from "./components/TaskForm.vue";
import TaskList from "./components/TaskList.vue";

export default {
  components: { TaskHeader, TaskForm, TaskList },
  name: "App",
  data() {
    return {
      tasks: ["Buy coffee", "Buy bacon", "Get a job at anchor"],
    };
  },
  methods: {
    addTask(text, clearInput) {
      if (!text.trim()) return;
      this.tasks = [...this.tasks, text];
      clearInput();
    },
    deleteTask(index) {
      this.tasks = this.tasks.filter((task, taskId) => taskId !== index);
    },
  },
};
</script>
