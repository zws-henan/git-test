<script setup>
import { ref } from 'vue'

const emit = defineEmits(['add'])

const taskText = ref('')

function handleAdd() {
  if (!taskText.value.trim()) return
  emit('add', taskText.value)
  taskText.value = ''
}
</script>

<template>
  <section class="add-task">
    <input
      type="text"
      class="task-input"
      v-model="taskText"
      placeholder="请输入任务内容..."
      @keyup.enter="handleAdd"
    >
    <button class="add-btn" @click="handleAdd">添加</button>
  </section>
</template>

<style scoped>
.add-task {
    display: flex;
    gap: 12px;
    margin-bottom: 24px;
}

.task-input {
    flex: 1;
    padding: 14px 18px;
    border: 2px solid #e0e0e0;
    border-radius: 8px;
    font-size: 15px;
    transition: border-color 0.3s ease;
    outline: none;
}

.task-input:focus {
    border-color: #667eea;
}

.add-btn {
    padding: 14px 28px;
    background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
    color: #fff;
    border: none;
    border-radius: 8px;
    font-size: 15px;
    font-weight: 600;
    cursor: pointer;
    transition: opacity 0.3s ease, transform 0.2s ease;
    white-space: nowrap;
}

.add-btn:hover {
    opacity: 0.9;
    transform: translateY(-1px);
}

.add-btn:active {
    transform: translateY(0);
}

@media (max-width: 480px) {
    .add-task {
        flex-direction: column;
    }

    .add-btn {
        width: 100%;
    }
}
</style>
