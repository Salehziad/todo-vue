<template>
  <header>
    <h1>{{ title }}</h1>
    <Button :text="showAddTask?'Close':'Add Task'" @showAdd="$emit('showAdd')" :color="showAddTask?'red':'green'" />
  </header>
</template>
<script>
    import Button from "../components/Button";

export default {
  name: "Header",
  components: {
    Button,
  },
  props: {
    title: String,
    showAddTask:Boolean
  },
  emit:['show-task']
};
</script>

<style scoped>
header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 20px;
}
</style>
