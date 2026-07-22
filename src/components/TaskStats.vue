<script setup>
import { computed } from 'vue'

const props = defineProps({
  tasks: {
    type: Array,
    default: () => []
  }
})

const total = computed(() => props.tasks.length)
const completedCount = computed(() => props.tasks.filter(t => t.completed).length)
const uncompletedCount = computed(() => total.value - completedCount.value)
</script>

<template>
  <section class="stats">
    <span class="stat-text">共 <strong>{{ total }}</strong> 项任务</span>
    <span class="stat-divider">|</span>
    <span class="stat-text">已完成 <strong>{{ completedCount }}</strong> 项</span>
    <span class="stat-divider">|</span>
    <span class="stat-text">未完成 <strong>{{ uncompletedCount }}</strong> 项</span>
  </section>
</template>

<style scoped>
.stats {
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 12px;
    padding: 16px;
    background: #f9f9f9;
    border-radius: 8px;
    margin-bottom: 16px;
}

.stat-text {
    font-size: 14px;
    color: #666;
}

.stat-text strong {
    color: #667eea;
    font-weight: 600;
}

.stat-divider {
    color: #ddd;
}

@media (max-width: 480px) {
    .stats {
        flex-direction: column;
        gap: 6px;
    }

    .stat-divider {
        display: none;
    }
}
</style>
