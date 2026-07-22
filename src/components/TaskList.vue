<script setup>
import TaskItem from './TaskItem.vue'

defineProps({
  tasks: {
    type: Array,
    default: () => []
  }
})
</script>

<template>
  <section class="task-list">
    <ul class="tasks">
      <TaskItem
        v-for="task in tasks"
        :key="task.id"
        :task="task"
      />
    </ul>
  </section>
</template>

<style scoped>
.task-list {
    margin-bottom: 24px;
}

.tasks {
    list-style: none;
}
</style>
