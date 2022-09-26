<template>
  <div>
    <div :key="task.id" v-for="task in tasks">
      <Task
        @toggle-reminder="$emit('toggle-reminder', task.id)"
        @delete-task="$emit('delete-task', task.id)"
        :task="task"
      />
    </div>
  </div>
</template>

<script>
export default {
  name: "Tasks",
  props: {
    tasks: Array,
  },
  emits: ["delete-task","toggle-reminder"],
  methods: {},
  mounted() {
    // console.log(this.tasks);
  },
};
</script>

<style lang="scss" scoped></style>
