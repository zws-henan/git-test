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
    border: 1px solid #3a3f4a;
    border-radius: 8px;
    font-size: 14px;
    font-weight: 500;
    cursor: pointer;
    transition: all 0.3s ease;
}

.clear-btn {
    background: #3d3826;
    color: #c8a96a;
    border-color: #5a4d2a;
}

.clear-btn:hover {
    background: #4a4230;
}

.clear-all-btn {
    background: #3d2629;
    color: #c9696e;
    border-color: #5a2a2e;
}

.clear-all-btn:hover {
    background: #4a3033;
}
</style>
