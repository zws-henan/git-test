<script setup>
import { ref } from 'vue'
import AppHeader from './components/AppHeader.vue'
import AddTask from './components/AddTask.vue'
import TaskFilter from './components/TaskFilter.vue'
import TaskList from './components/TaskList.vue'
import TaskStats from './components/TaskStats.vue'
import TaskActions from './components/TaskActions.vue'
import AppFooter from './components/AppFooter.vue'

// 任务列表数据
const tasks = ref([
  { id: 1, text: '学习 JavaScript 基础语法', completed: false },
  { id: 2, text: '完成项目设计文档', completed: false },
  { id: 3, text: '回复邮件', completed: false },
  { id: 4, text: '购买日用品', completed: true },
  { id: 5, text: '整理书桌', completed: true }
])

// 添加任务
function handleAddTask(text) {
  if (!text.trim()) return
  tasks.value.push({
    id: Date.now(),
    text: text.trim(),
    completed: false
  })
}
</script>

<template>
  <div class="container">
    <AppHeader />

    <main class="main">
      <AddTask @add="handleAddTask" />
      <TaskFilter />
      <TaskList :tasks="tasks" />
      <TaskStats :tasks="tasks" />
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
    background: #1a1d24;
    min-height: 100vh;
    color: #e4e6eb;
    display: flex;
    justify-content: center;
    align-items: flex-start;
    padding: 40px 20px;
}

/* 容器 */
.container {
    width: 100%;
    max-width: 600px;
    background: #252932;
    border-radius: 16px;
    box-shadow: 0 20px 60px rgba(0, 0, 0, 0.5);
    overflow: hidden;
    border: 1px solid #3a3f4a;
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
