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
    border-bottom: 1px solid #f0f0f0;
}

.filter-btn {
    flex: 1;
    padding: 10px;
    background: #f5f5f5;
    border: none;
    border-radius: 6px;
    font-size: 14px;
    color: #666;
    cursor: pointer;
    transition: all 0.3s ease;
}

.filter-btn:hover {
    background: #ebebeb;
}

.filter-btn.active {
    background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
    color: #fff;
}

@media (max-width: 480px) {
    .filter-btn {
        font-size: 13px;
        padding: 8px;
    }
}
</style>
