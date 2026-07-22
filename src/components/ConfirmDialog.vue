<script setup>
defineProps({
  visible: {
    type: Boolean,
    default: false
  },
  message: {
    type: String,
    default: '确定要删除这条任务吗？'
  }
})

const emit = defineEmits(['confirm', 'cancel'])
</script>

<template>
  <Transition name="bubble">
    <div v-if="visible" class="confirm-bubble" role="dialog" aria-modal="true">
      <span class="bubble-arrow"></span>
      <p class="bubble-message">{{ message }}</p>
      <div class="bubble-actions">
        <button class="bubble-btn cancel-btn" @click="emit('cancel')">取消</button>
        <button class="bubble-btn confirm-btn" @click="emit('confirm')">确认删除</button>
      </div>
    </div>
  </Transition>
</template>

<style scoped>
.confirm-bubble {
    position: absolute;
    top: calc(100% + 10px);
    right: 0;
    background: #2d3139;
    border: 1px solid #3a3f4a;
    border-radius: 12px;
    padding: 14px 16px;
    width: 220px;
    box-shadow: 0 8px 24px rgba(0, 0, 0, 0.5);
    z-index: 1000;
}

/* 气泡小箭头，指向触发按钮 */
.bubble-arrow {
    position: absolute;
    top: -6px;
    right: 18px;
    width: 12px;
    height: 12px;
    background: #2d3139;
    border-top: 1px solid #3a3f4a;
    border-left: 1px solid #3a3f4a;
    transform: rotate(45deg);
    border-top-left-radius: 3px;
}

.bubble-message {
    font-size: 14px;
    color: #e4e6eb;
    margin-bottom: 12px;
    line-height: 1.5;
}

.bubble-actions {
    display: flex;
    gap: 8px;
    justify-content: flex-end;
}

.bubble-btn {
    padding: 6px 14px;
    border: none;
    border-radius: 6px;
    font-size: 13px;
    font-weight: 500;
    cursor: pointer;
    transition: all 0.25s ease;
}

.cancel-btn {
    background: #3a3f4a;
    color: #e4e6eb;
}

.cancel-btn:hover {
    background: #4a5060;
}

.confirm-btn {
    background: linear-gradient(135deg, #c9696e 0%, #a85a5e 100%);
    color: #fff;
}

.confirm-btn:hover {
    opacity: 0.9;
    transform: translateY(-1px);
}

/* 气泡过渡动画：从触发点缩放展开 */
.bubble-enter-active,
.bubble-leave-active {
    transition: opacity 0.2s ease, transform 0.2s ease;
    transform-origin: top right;
}

.bubble-enter-from,
.bubble-leave-to {
    opacity: 0;
    transform: scale(0.85) translateY(-4px);
}
</style>
