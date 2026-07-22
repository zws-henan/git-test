<script setup>
import AppHeader from './components/AppHeader.vue'
import AddTask from './components/AddTask.vue'
import TaskFilter from './components/TaskFilter.vue'
import TaskList from './components/TaskList.vue'
import TaskStats from './components/TaskStats.vue'
import TaskActions from './components/TaskActions.vue'
import AppFooter from './components/AppFooter.vue'
</script>

<template>
  <div class="container">
    <AppHeader />

    <main class="main">
      <AddTask />
      <TaskFilter />
      <TaskList />
      <TaskStats />
      <TaskActions />
    </main>

    <AppFooter />
  </div>
</template>

<style>
/* 全局重置 */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

/* 基础样式 */
body {
    font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", "PingFang SC",
                 "Hiragino Sans GB", "Microsoft YaHei", sans-serif;
    background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
    min-height: 100vh;
    color: #333;
    display: flex;
    justify-content: center;
    align-items: flex-start;
    padding: 40px 20px;
}

/* 容器 */
.container {
    width: 100%;
    max-width: 600px;
    background: #fff;
    border-radius: 16px;
    box-shadow: 0 20px 60px rgba(0, 0, 0, 0.3);
    overflow: hidden;
}

/* 主体内容 */
.main {
    padding: 30px 40px;
}

@media (max-width: 480px) {
    .main {
        padding: 20px;
    }
}
</style>
