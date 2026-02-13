<script setup>
import { watch, useTemplateRef } from "vue";

// 定义通用的属性配置
const props = defineProps({
  // 模态框标题
  title: {
    type: String,
    default: "确认操作"
  },
  // 提示文本（支持自定义任意操作的提示）
  message: {
    type: String,
    default: "你确定要执行此操作吗？"
  },
  // 确认按钮文字
  confirmText: {
    type: String,
    default: "确认"
  },
  // 取消按钮文字
  cancelText: {
    type: String,
    default: "取消"
  },
  // 确认按钮样式（支持自定义，比如删除用error、修改用primary）
  confirmBtnType: {
    type: String,
    default: "btn-primary", // 默认primary，删除可用btn-error
    validator: (value) => {
      // 限制可选的样式类型，保证符合项目规范
      return ['btn-primary', 'btn-error', 'btn-success', 'btn-warning'].includes(value);
    }
  },
  // 是否显示模态框（受控属性）
  modelValue: {
    type: Boolean,
    default: false
  }
});

// 定义触发的事件
const emit = defineEmits([
  // v-model 双向绑定事件
  "update:modelValue",
  // 确认操作事件
  "confirm",
  // 取消操作事件
  "cancel"
]);

// 模态框引用
const modalRef = useTemplateRef("modal-ref");

// 监听 modelValue 变化，自动控制模态框显示/隐藏
watch(
  () => props.modelValue,
  (newVal) => {
    if (newVal) {
      modalRef.value?.showModal();
    } else {
      modalRef.value?.close();
    }
  },
  { immediate: true } // 初始值生效
);

// 关闭模态框的通用方法
const closeModal = () => {
  emit("update:modelValue", false);
};

// 确认操作
const handleConfirm = () => {
  emit("confirm");
  closeModal();
};

// 取消操作
const handleCancel = () => {
  emit("cancel");
  closeModal();
};
</script>

<template>
  <dialog ref="modal-ref" class="modal" @close="emit('update:modelValue', false)">
    <div class="modal-box">
      <!-- 自定义标题 -->
      <h3 class="font-bold text-lg">{{ title }}</h3>
      <!-- 自定义提示文本 -->
      <p class="py-4">{{ message }}</p>
      <!-- 自定义操作按钮 -->
      <div class="modal-action">
        <button @click="handleCancel" class="btn">{{ cancelText }}</button>
        <button @click="handleConfirm" :class="['btn', confirmBtnType]">{{ confirmText }}</button>
      </div>
    </div>
  </dialog>
</template>

<style scoped>
/* 基础样式，可根据项目调整 */
.modal-box {
  border-radius: 8px;
  min-width: 300px;
}
</style>