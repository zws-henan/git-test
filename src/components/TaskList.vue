<script setup>
import TaskItem from './TaskItem.vue'
</script>

<template>
  <section class="task-list">
    <ul class="tasks">
      <!-- 未完成任务 -->
      <TaskItem text="学习 JavaScript 基础语法" />
      <TaskItem text="完成项目设计文档" />
      <TaskItem text="回复邮件" />

      <!-- 已完成任务 -->
      <TaskItem text="购买日用品" completed />
      <TaskItem text="整理书桌" completed />
    </ul>
  </section>
</template>

<style scoped>
.task-list {
    margin-bottom: 24px;
}

.tasks {
    list-style: none;
}
</style>
