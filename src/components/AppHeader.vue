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
    background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
    color: #fff;
    padding: 30px 40px;
    text-align: center;
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
