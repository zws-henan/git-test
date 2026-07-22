<script setup>
import { ref } from 'vue'
import ConfirmDialog from './ConfirmDialog.vue'

const props = defineProps({
  task: {
    type: Object,
    required: true
  }
})

const emit = defineEmits(['delete'])

const confirming = ref(false)

// 点击删除：先弹出气泡确认框，不直接删除
function handleDeleteClick() {
  confirming.value = true
}

function handleConfirm() {
  confirming.value = false
  emit('delete', props.task.id)
}

function handleCancel() {
  confirming.value = false
}
</script>

<template>
  <li class="task-item" :class="{ completed: task.completed }">
    <label class="checkbox-wrap">
      <input type="checkbox" :checked="task.completed">
      <span class="checkbox-custom"></span>
    </label>
    <span class="task-text">{{ task.text }}</span>
    <div class="delete-wrap">
      <button class="delete-btn" @click="handleDeleteClick">删除</button>
      <ConfirmDialog
        :visible="confirming"
        message="确定要删除这条任务吗？"
        @confirm="handleConfirm"
        @cancel="handleCancel"
      />
    </div>
    <!-- 点击气泡外部时关闭 -->
    <div v-if="confirming" class="outside-catch" @click="handleCancel"></div>
  </li>
</template>

<style scoped>
.task-item {
    display: flex;
    align-items: center;
    padding: 16px 0;
    border-bottom: 1px solid #3a3f4a;
    transition: background-color 0.2s ease;
}

.task-item:hover {
    background-color: #2d3139;
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
    border: 2px solid #4a5060;
    border-radius: 50%;
    position: relative;
    transition: all 0.3s ease;
}

.checkbox-wrap input[type="checkbox"]:checked ~ .checkbox-custom {
    background: linear-gradient(135deg, #3d4a6b 0%, #4a3d6b 100%);
    border-color: transparent;
}

.checkbox-wrap input[type="checkbox"]:checked ~ .checkbox-custom::after {
    content: "";
    position: absolute;
    left: 6px;
    top: 2px;
    width: 6px;
    height: 11px;
    border: solid #e4e6eb;
    border-width: 0 2px 2px 0;
    transform: rotate(45deg);
}

/* 任务文本 */
.task-text {
    flex: 1;
    font-size: 15px;
    color: #e4e6eb;
    transition: all 0.3s ease;
}

.task-item.completed .task-text {
    color: #6b7280;
    text-decoration: line-through;
}

/* 删除按钮 */
.delete-btn {
    padding: 6px 14px;
    background: transparent;
    color: #c9696e;
    border: 1px solid #c9696e;
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
    background: #c9696e;
    color: #e4e6eb;
}

/* 删除按钮容器：作为气泡框的定位锚点 */
.delete-wrap {
    position: relative;
}

/* 透明遮罩：点击气泡外部时关闭，不影响气泡自身交互 */
.outside-catch {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    z-index: 999;
}

@media (max-width: 480px) {
    .delete-btn {
        opacity: 1;
    }
}
</style>
