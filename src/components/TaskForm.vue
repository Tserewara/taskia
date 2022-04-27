<template>
  <div>
    <input v-model="text" type="text" placeholder="Add Task" />
    <button @click="$emit('btn-click', text, clearInput)">Add</button>
  </div>
</template>

<script>
export default {
  name: "TaskForm",
  data() {
    return {
      text: "",
    };
  },
  methods: {
    clearInput() {
      this.text = "";
    },
  },
};
</script>
