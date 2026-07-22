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
    background: #2a2e37;
    border-radius: 8px;
    margin-bottom: 16px;
    border: 1px solid #3a3f4a;
}

.stat-text {
    font-size: 14px;
    color: #9ca3af;
}

.stat-text strong {
    color: #7c8db5;
    font-weight: 600;
}

.stat-divider {
    color: #4a5060;
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
