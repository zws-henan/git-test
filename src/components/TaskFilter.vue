<script setup>

</script>

<template>
  <section class="filter">
    <button class="filter-btn active">全部</button>
    <button class="filter-btn">未完成</button>
    <button class="filter-btn">已完成</button>
  </section>
</template>

<style scoped>
.filter {
    display: flex;
    gap: 8px;
    margin-bottom: 20px;
    padding-bottom: 20px;
    border-bottom: 1px solid #3a3f4a;
}

.filter-btn {
    flex: 1;
    padding: 10px;
    background: #2a2e37;
    border: 1px solid #3a3f4a;
    border-radius: 6px;
    font-size: 14px;
    color: #9ca3af;
    cursor: pointer;
    transition: all 0.3s ease;
}

.filter-btn:hover {
    background: #323742;
}

.filter-btn.active {
    background: linear-gradient(135deg, #3d4a6b 0%, #4a3d6b 100%);
    color: #e4e6eb;
    border-color: #4a5068;
}

@media (max-width: 480px) {
    .filter-btn {
        font-size: 13px;
        padding: 8px;
    }
}
</style>
