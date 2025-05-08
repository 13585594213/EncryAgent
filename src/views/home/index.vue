<template>
  <div class="home-container">
    <h1 class="welcome-title">欢迎使用 EncryAgent</h1>
    <p class="welcome-subtitle">您的智能加密助手</p>
    <div class="feature-list">
      <div class="feature-item">
        <h3>安全可靠</h3>
        <p>采用先进的加密技术，保护您的数据安全</p>
      </div>
      <div class="feature-item">
        <h3>简单易用</h3>
        <p>直观的界面设计，让加密操作变得简单</p>
      </div>
      <div class="feature-item">
        <h3>功能强大</h3>
        <p>支持多种加密算法，满足不同场景需求</p>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
// 组件逻辑
</script>

<style scoped>
.home-container {
  padding: 2rem;
  max-width: 1200px;
  margin: 0 auto;
}

.welcome-title {
  font-size: 2.5rem;
  color: #333;
  text-align: center;
  margin-bottom: 1rem;
}

.welcome-subtitle {
  font-size: 1.5rem;
  color: #666;
  text-align: center;
  margin-bottom: 3rem;
}

.feature-list {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 2rem;
  margin-top: 2rem;
}

.feature-item {
  padding: 1.5rem;
  background-color: #f5f5f5;
  border-radius: 8px;
  text-align: center;
}

.feature-item h3 {
  color: #333;
  margin-bottom: 1rem;
}

.feature-item p {
  color: #666;
  line-height: 1.6;
}
</style> 