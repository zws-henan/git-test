<script setup>

</script>

<template>
  <section class="actions">
    <button class="clear-btn">清除已完成</button>
    <button class="clear-all-btn">清除全部</button>
  </section>
</template>

<style scoped>
.actions {
    display: flex;
    gap: 12px;
}

.clear-btn,
.clear-all-btn {
    flex: 1;
    padding: 12px;
    border: none;
    border-radius: 8px;
    font-size: 14px;
    font-weight: 500;
    cursor: pointer;
    transition: all 0.3s ease;
}

.clear-btn {
    background: #fff3cd;
    color: #856404;
}

.clear-btn:hover {
    background: #ffeaa7;
}

.clear-all-btn {
    background: #f8d7da;
    color: #721c24;
}

.clear-all-btn:hover {
    background: #fab1a0;
}
</style>
