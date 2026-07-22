<script setup>

</script>

<template>
  <section class="stats">
    <span class="stat-text">共 <strong>5</strong> 项任务</span>
    <span class="stat-divider">|</span>
    <span class="stat-text">已完成 <strong>2</strong> 项</span>
    <span class="stat-divider">|</span>
    <span class="stat-text">未完成 <strong>3</strong> 项</span>
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
