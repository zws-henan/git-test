<script setup lang="ts">

</script>

<template>
  <div class="container">
    <header class="header">
      <h1 class="title">To-Do List</h1>
      <p class="subtitle">管理你的日常任务</p>
    </header>

    <main class="main">
      <!-- 添加任务区域 -->
      <section class="add-task">
        <input type="text" class="task-input" placeholder="请输入任务内容...">
        <button class="add-btn">添加</button>
      </section>

      <!-- 过滤器区域 -->
      <section class="filter">
        <button class="filter-btn active">全部</button>
        <button class="filter-btn">未完成</button>
        <button class="filter-btn">已完成</button>
      </section>

      <!-- 任务列表区域 -->
      <section class="task-list">
        <ul class="tasks">
          <!-- 未完成任务 -->
          <li class="task-item">
            <label class="checkbox-wrap">
              <input type="checkbox">
              <span class="checkbox-custom"></span>
            </label>
            <span class="task-text">学习 JavaScript 基础语法</span>
            <button class="delete-btn">删除</button>
          </li>

          <li class="task-item">
            <label class="checkbox-wrap">
              <input type="checkbox">
              <span class="checkbox-custom"></span>
            </label>
            <span class="task-text">完成项目设计文档</span>
            <button class="delete-btn">删除</button>
          </li>

          <li class="task-item">
            <label class="checkbox-wrap">
              <input type="checkbox">
              <span class="checkbox-custom"></span>
            </label>
            <span class="task-text">回复邮件</span>
            <button class="delete-btn">删除</button>
          </li>

          <!-- 已完成任务 -->
          <li class="task-item completed">
            <label class="checkbox-wrap">
              <input type="checkbox" checked>
              <span class="checkbox-custom"></span>
            </label>
            <span class="task-text">购买日用品</span>
            <button class="delete-btn">删除</button>
          </li>

          <li class="task-item completed">
            <label class="checkbox-wrap">
              <input type="checkbox" checked>
              <span class="checkbox-custom"></span>
            </label>
            <span class="task-text">整理书桌</span>
            <button class="delete-btn">删除</button>
          </li>
        </ul>
      </section>

      <!-- 统计信息区域 -->
      <section class="stats">
        <span class="stat-text">共 <strong>5</strong> 项任务</span>
        <span class="stat-divider">|</span>
        <span class="stat-text">已完成 <strong>2</strong> 项</span>
        <span class="stat-divider">|</span>
        <span class="stat-text">未完成 <strong>3</strong> 项</span>
      </section>

      <!-- 清除按钮 -->
      <section class="actions">
        <button class="clear-btn">清除已完成</button>
        <button class="clear-all-btn">清除全部</button>
      </section>
    </main>

    <footer class="footer">
      <p>&copy; 2026 To-Do List 应用</p>
    </footer>
  </div>
</template>

<style scoped>
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

/* 头部 */
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

/* 主体内容 */
.main {
    padding: 30px 40px;
}

/* 添加任务区域 */
.add-task {
    display: flex;
    gap: 12px;
    margin-bottom: 24px;
}

.task-input {
    flex: 1;
    padding: 14px 18px;
    border: 2px solid #e0e0e0;
    border-radius: 8px;
    font-size: 15px;
    transition: border-color 0.3s ease;
    outline: none;
}

.task-input:focus {
    border-color: #667eea;
}

.add-btn {
    padding: 14px 28px;
    background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
    color: #fff;
    border: none;
    border-radius: 8px;
    font-size: 15px;
    font-weight: 600;
    cursor: pointer;
    transition: opacity 0.3s ease, transform 0.2s ease;
    white-space: nowrap;
}

.add-btn:hover {
    opacity: 0.9;
    transform: translateY(-1px);
}

.add-btn:active {
    transform: translateY(0);
}

/* 过滤器区域 */
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

/* 任务列表 */
.task-list {
    margin-bottom: 24px;
}

.tasks {
    list-style: none;
}

.task-item {
    display: flex;
    align-items: center;
    padding: 16px 0;
    border-bottom: 1px solid #f0f0f0;
    transition: background-color 0.2s ease;
}

.task-item:hover {
    background-color: #fafafa;
}

.task-item:last-child {
    border-bottom: none;
}

/* 自定义复选框 */
.checkbox-wrap {
    position: relative;
    display: inline-block;
    margin-right: 16px;
    cursor: pointer;
}

.checkbox-wrap input[type="checkbox"] {
    opacity: 0;
    position: absolute;
    width: 100%;
    height: 100%;
    cursor: pointer;
}

.checkbox-custom {
    display: block;
    width: 22px;
    height: 22px;
    border: 2px solid #d0d0d0;
    border-radius: 50%;
    position: relative;
    transition: all 0.3s ease;
}

.checkbox-wrap input[type="checkbox"]:checked ~ .checkbox-custom {
    background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
    border-color: transparent;
}

.checkbox-wrap input[type="checkbox"]:checked ~ .checkbox-custom::after {
    content: "";
    position: absolute;
    left: 6px;
    top: 2px;
    width: 6px;
    height: 11px;
    border: solid #fff;
    border-width: 0 2px 2px 0;
    transform: rotate(45deg);
}

/* 任务文本 */
.task-text {
    flex: 1;
    font-size: 15px;
    color: #333;
    transition: all 0.3s ease;
}

.task-item.completed .task-text {
    color: #aaa;
    text-decoration: line-through;
}

/* 删除按钮 */
.delete-btn {
    padding: 6px 14px;
    background: transparent;
    color: #ff6b6b;
    border: 1px solid #ff6b6b;
    border-radius: 6px;
    font-size: 13px;
    cursor: pointer;
    transition: all 0.3s ease;
    opacity: 0;
}

.task-item:hover .delete-btn {
    opacity: 1;
}

.delete-btn:hover {
    background: #ff6b6b;
    color: #fff;
}

/* 统计信息 */
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

/* 操作按钮 */
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

/* 底部 */
.footer {
    padding: 20px 40px;
    background: #fafafa;
    text-align: center;
    border-top: 1px solid #f0f0f0;
}

.footer p {
    font-size: 13px;
    color: #999;
}

/* 响应式设计 */
@media (max-width: 480px) {
    .header {
        padding: 24px 20px;
    }

    .title {
        font-size: 26px;
    }

    .main {
        padding: 20px;
    }

    .add-task {
        flex-direction: column;
    }

    .add-btn {
        width: 100%;
    }

    .filter-btn {
        font-size: 13px;
        padding: 8px;
    }

    .delete-btn {
        opacity: 1;
    }

    .stats {
        flex-direction: column;
        gap: 6px;
    }

    .stat-divider {
        display: none;
    }
}
</style>
