<template>
  <!-- 我们给每个关键元素添加一个 class，以便在 <style> 中定位它们 -->
  <header class="top-header">
    <div class="header-container">

      <!-- 左侧 (柔性区域) -->
      <div class="header-left">
        <n-icon size="24" color="#3b82f6">
          <Bot />
        </n-icon>
        <h1 class="header-title">Multi-Agent System</h1>
      </div>
      
      <!-- 右侧 (刚性区域) -->
      <div class="header-right">
        <n-tooltip trigger="hover">
          <template #trigger>
            <n-button ghost>
              <template #icon>
                <n-icon>
                  <MessageSquare />
                </n-icon>
              </template>
              会话管理
            </n-button>
          </template>
          管理和查看所有会话历史记录
        </n-tooltip>
        
        <n-tooltip trigger="hover">
          <template #trigger>
            <n-button ghost>
              <template #icon>
                <n-icon>
                  <Users />
                </n-icon>
              </template>
              AI角色
            </n-button>
          </template>
          配置不同的AI助手角色和能力
        </n-tooltip>
        
        <n-tooltip trigger="hover">
          <template #trigger>
            <n-button ghost>
              <template #icon>
                <n-icon>
                  <Settings />
                </n-icon>
              </template>
              设置
            </n-button>
          </template>
          系统设置和偏好配置
        </n-tooltip>
      </div>
    </div>
  </header>
</template>

<script setup lang="ts">
import { NButton, NIcon, NTooltip } from 'naive-ui'
import { Bot, MessageSquare, Users, Settings } from 'lucide-vue-next'
</script>

<style scoped>
/* 外部 header 样式 */
.top-header {
  background-color: white;
  border-bottom: 1px solid #e5e7eb; /* 对应 border-gray-200 */
  padding: 1rem 1.5rem; /* 对应 px-6 py-4 */
}

/* 核心 Flexbox 容器 */
.header-container {
  display: flex;
  align-items: center;
  justify-content: space-between; /* 将左右两部分推到两端 */
  gap: 1rem; /* 在元素可能接触时提供一些间距 */
}

/* 左侧区域：图标和标题 */
.header-left {
  display: flex;
  align-items: center;
  gap: 0.75rem; /* 对应 space-x-3 */

  /* 这是解决问题的关键！ */
  min-width: 0; /* 允许这个容器收缩到比其内容更窄 */
}

/* 标题样式 */
.header-title {
  font-size: 1.25rem; /* 对应 text-xl */
  font-weight: 600;   /* 对应 font-semibold */
  color: #111827;      /* 对应 text-gray-900 */
  
  /* 这是解决问题的另一个关键！ */
  white-space: nowrap;      /* 防止文字自身换行 */
  overflow: hidden;         /* 隐藏溢出的部分 */
  text-overflow: ellipsis;  /* 将溢出的部分显示为省略号 */
}

/* 右侧区域：按钮组 */
.header-right {
  display: flex;
  align-items: center;
  gap: 1rem; /* 对应 space-x-4 */
  
  /* 这是确保右侧稳定的关键！ */
  flex-shrink: 0; /* 禁止这个容器收缩 */
}
</style>