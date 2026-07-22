<script setup>

</script>

<template>
  <header class="header">
    <h1 class="title">To-Do List</h1>
    <p class="subtitle">管理你的日常任务</p>
  </header>
</template>

<style scoped>
.header {
    background: linear-gradient(135deg, #2d3548 0%, #3d2d48 100%);
    color: #e4e6eb;
    padding: 30px 40px;
    text-align: center;
    border-bottom: 1px solid #3a3f4a;
}

.title {
    font-size: 32px;
    font-weight: 700;
    margin-bottom: 8px;
}

.subtitle {
    font-size: 14px;
    opacity: 0.9;
}

@media (max-width: 480px) {
    .header {
        padding: 24px 20px;
    }

    .title {
        font-size: 26px;
    }
}
</style>
