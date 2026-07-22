<script setup>
import TaskItem from './TaskItem.vue'

defineProps({
  tasks: {
    type: Array,
    default: () => []
  }
})

const emit = defineEmits(['delete'])
</script>

<template>
  <section class="task-list">
    <ul class="tasks">
      <TaskItem
        v-for="task in tasks"
        :key="task.id"
        :task="task"
        @delete="emit('delete', $event)"
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
