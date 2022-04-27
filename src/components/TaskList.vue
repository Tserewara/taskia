<template>
  <ul>
    <li :key="index" v-for="(task, index) in tasks">
      {{ task }}
      <span @click="$emit('span-click', index)">&#9940;</span>
    </li>
  </ul>
</template>

<script>
export default {
  name: "TaskList",
  props: {
    tasks: Array,
  },
};
</script>

<style scoped>
span {
  cursor: pointer;
}
</style>
