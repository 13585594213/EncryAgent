<template>
  <div class="price-container">
    <h1 class="page-title">价格方案</h1>
    <div class="price-cards">
      <div class="price-card">
        <h2 class="card-title">基础版</h2>
        <div class="price">
          <span class="amount">¥99</span>
          <span class="period">/月</span>
        </div>
        <ul class="features">
          <li>基础加密功能</li>
          <li>标准技术支持</li>
          <li>基础API访问</li>
        </ul>
        <button class="select-btn">立即选择</button>
      </div>

      <div class="price-card featured">
        <h2 class="card-title">专业版</h2>
        <div class="price">
          <span class="amount">¥299</span>
          <span class="period">/月</span>
        </div>
        <ul class="features">
          <li>高级加密功能</li>
          <li>优先技术支持</li>
          <li>完整API访问</li>
          <li>自定义配置</li>
        </ul>
        <button class="select-btn">立即选择</button>
      </div>

      <div class="price-card">
        <h2 class="card-title">企业版</h2>
        <div class="price">
          <span class="amount">¥999</span>
          <span class="period">/月</span>
        </div>
        <ul class="features">
          <li>企业级加密功能</li>
          <li>24/7专属支持</li>
          <li>无限API访问</li>
          <li>高级定制服务</li>
          <li>专属客户经理</li>
        </ul>
        <button class="select-btn">立即选择</button>
      </div>
    </div>
  </div>
</template>

<style scoped>
.price-container {
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

.price-cards {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 2rem;
  padding: 1rem;
}

.price-card {
  background: white;
  border-radius: 12px;
  padding: 2rem;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  transition: transform 0.3s ease;
}

.price-card:hover {
  transform: translateY(-5px);
}

.price-card.featured {
  border: 2px solid var(--primary-color);
  transform: scale(1.05);
}

.price-card.featured:hover {
  transform: scale(1.05) translateY(-5px);
}

.card-title {
  font-size: 1.5rem;
  color: #333;
  text-align: center;
  margin-bottom: 1rem;
}

.price {
  text-align: center;
  margin-bottom: 2rem;
}

.amount {
  font-size: 3rem;
  font-weight: bold;
  color: var(--primary-color);
}

.period {
  font-size: 1rem;
  color: #666;
}

.features {
  list-style: none;
  padding: 0;
  margin: 0 0 2rem 0;
}

.features li {
  padding: 0.5rem 0;
  color: #666;
  text-align: center;
  position: relative;
}

.features li::before {
  content: "✓";
  color: var(--primary-color);
  margin-right: 0.5rem;
}

.select-btn {
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

.select-btn:hover {
  background-color: var(--primary-color-dark);
}
</style> 