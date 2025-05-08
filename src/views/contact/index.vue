<template>
  <div class="contact-container">
    <h1 class="page-title">联系我们</h1>
    <div class="contact-content">
      <div class="contact-info">
        <div class="info-card">
          <h3>联系方式</h3>
          <ul>
            <li>
              <i class="icon-phone"></i>
              <span>电话：400-123-4567</span>
            </li>
            <li>
              <i class="icon-email"></i>
              <span>邮箱：support@encryagent.com</span>
            </li>
            <li>
              <i class="icon-address"></i>
              <span>地址：北京市朝阳区科技园区88号</span>
            </li>
          </ul>
        </div>
        <div class="info-card">
          <h3>工作时间</h3>
          <ul>
            <li>周一至周五：9:00 - 18:00</li>
            <li>周六：10:00 - 16:00</li>
            <li>周日：休息</li>
          </ul>
        </div>
      </div>
      <div class="contact-form">
        <h3>发送消息</h3>
        <form @submit.prevent="handleSubmit">
          <div class="form-group">
            <label for="name">姓名</label>
            <input type="text" id="name" v-model="form.name" required>
          </div>
          <div class="form-group">
            <label for="email">邮箱</label>
            <input type="email" id="email" v-model="form.email" required>
          </div>
          <div class="form-group">
            <label for="message">消息</label>
            <textarea id="message" v-model="form.message" rows="5" required></textarea>
          </div>
          <button type="submit" class="submit-btn">发送消息</button>
        </form>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { reactive } from 'vue';

const form = reactive({
  name: '',
  email: '',
  message: ''
});

const handleSubmit = () => {
  // TODO: 实现表单提交逻辑
  console.log('Form submitted:', form);
};
</script>

<style scoped>
.contact-container {
  padding: 2rem;
  max-width: 1200px;
  margin: 0 auto;
}

.page-title {
  text-align: center;
  font-size: 2.5rem;
  color: #333;
  margin-bottom: 3rem;
}

.contact-content {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 2rem;
  padding: 1rem;
}

.contact-info {
  display: flex;
  flex-direction: column;
  gap: 2rem;
}

.info-card {
  background: white;
  border-radius: 12px;
  padding: 2rem;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
}

.info-card h3 {
  font-size: 1.5rem;
  color: #333;
  margin-bottom: 1rem;
}

.info-card ul {
  list-style: none;
  padding: 0;
  margin: 0;
}

.info-card li {
  padding: 0.5rem 0;
  color: #666;
  display: flex;
  align-items: center;
  gap: 0.5rem;
}

.contact-form {
  background: white;
  border-radius: 12px;
  padding: 2rem;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
}

.contact-form h3 {
  font-size: 1.5rem;
  color: #333;
  margin-bottom: 1.5rem;
}

.form-group {
  margin-bottom: 1.5rem;
}

.form-group label {
  display: block;
  margin-bottom: 0.5rem;
  color: #666;
}

.form-group input,
.form-group textarea {
  width: 100%;
  padding: 0.75rem;
  border: 1px solid #ddd;
  border-radius: 6px;
  font-size: 1rem;
}

.form-group textarea {
  resize: vertical;
}

.submit-btn {
  width: 100%;
  padding: 1rem;
  border: none;
  border-radius: 6px;
  background-color: var(--primary-color);
  color: white;
  font-size: 1rem;
  cursor: pointer;
  transition: background-color 0.3s ease;
}

.submit-btn:hover {
  background-color: var(--primary-color-dark);
}

@media (max-width: 768px) {
  .contact-content {
    grid-template-columns: 1fr;
  }
}
</style> 