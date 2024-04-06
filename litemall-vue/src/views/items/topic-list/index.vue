<template>
  <div class="brand_culture">
    <!-- 介绍 -->
    <div class="section introduction">
      <h2>介绍</h2>
      <p>致力于打造线上饮品购物的网站。在我们这里应用尽有。没有你买不到的，只有你想不到的。</p>
    </div>

    <!-- 文化 -->
    <div class="section culture">
      <h2>文化</h2>
      <ul>
        <li>以客户为中心，不断满足客户需求。</li>
        <li>不断学习和进步，追求个人成长。</li>
        <li>开放包容，欢迎多元文化和观念。</li>
        <li>诚信经营，建立长期合作伙伴关系。</li>
      </ul>
    </div>

    <!-- 故事 -->
    <div class="section story">
      <h2>故事</h2>
      <p>
        创始人 Jenny 回到城市后，开始研发各种以天然植物和果实为基础的茶饮。
        他坚持使用有机原料，手工采摘，并融入传统茶艺，希望每一杯茶饮都能让消费者感受到大自然的魅力。
        后续还研究了其他各种各样的饮品。
      </p>
    </div>

    <!-- 历程 -->
    <div class="section course">
      <h2>历程</h2>
      <p>无</p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'BrandCulture'
};
</script>

<style scoped>
.brand_culture {
  padding: 20px;
}

.section {
  margin-bottom: 50px;
  border-bottom: 2px solid #eee;
  padding-bottom: 30px;
}

h2 {
  font-size: 28px;
  color: #333;
  margin-bottom: 20px;
}

p {
  font-size: 20px;
  color: #666;
  line-height: 1.8;
}

ul {
  list-style: none;
  padding-left: 0;
}

li {
  font-size: 20px;
  color: #666;
  margin-bottom: 15px;
}

/* 以下是一些额外的样式，使页面更具吸引力 */
.brand_culture {
  background-color: #f8f8f8;
}

.section {
  background-color: #fff;
  border-radius: 10px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  padding: 30px;
}

h2 {
  font-weight: bold;
  text-align: center;
}

.story p {
  text-indent: 2em;
}

.course p {
  text-align: center;
}
</style>
