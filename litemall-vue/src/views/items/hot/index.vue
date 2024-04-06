<template>
  <div class="franchise">
    <!-- 加盟顶部Banner -->
    <div class="banner">
      <div class="title">加入我们，共创美好未来</div>
    </div>

    <!-- 加盟优势 -->
    <div class="advantages">
      <h2>加盟优势</h2>
      <ul>
        <li>全方位培训，助您快速上手</li>
        <li>品牌知名，客户口碑好</li>
        <li>原料新鲜，独特口味，畅销市场</li>
        <li>总部提供一对一的运营指导和支持</li>
      </ul>
    </div>

    <!-- 加盟申请表单 -->
    <div class="form">
      <h2>加盟申请</h2>
      <form @submit.prevent="submitForm">
        <van-field v-model="formData.name" label="姓名" placeholder="请输入您的姓名" />
        <van-field v-model="formData.phone" label="电话" placeholder="请输入您的联系电话" type="tel" />
        <van-field v-model="formData.email" label="邮箱" placeholder="请输入您的邮箱" type="email" />
        <van-field v-model="formData.city" label="所在城市" placeholder="请输入您所在的城市" />
        <van-button type="primary" native-type="submit" class="submit-btn">提交申请</van-button>
      </form>
    </div>
  </div>
</template>

<script>
import { Field, Button } from 'vant';

export default {
  components: {
    VanField: Field,
    VanButton: Button
  },
  data() {
    return {
      formData: {
        name: '',
        phone: '',
        email: '',
        city: ''
      }
    };
  },
  methods: {
    submitForm() {
      // 提交表单逻辑
      console.log('表单已提交');
      // 清空表单
      this.formData = {
        name: '',
        phone: '',
        email: '',
        city: ''
      };
      this.$toast('已收到您的申请，会尽快联系您');
      this.$router.push('/');
    }
  }
};
</script>

<style scoped>
.franchise {
  padding: 20px;
}

.banner {
  height: 300px;
  background-size: cover;
  background-position: center;
  text-align: center;
  display: flex;
  align-items: center;
  justify-content: center;
}

.title {
  font-size: 36px;
  color: #bb6262;
}   

.advantages h2,
.form h2 {
  font-size: 28px;
  color: #333;
  margin-bottom: 20px;
}

.advantages ul {
  list-style: none;
  padding-left: 0;
}

.advantages li {
  font-size: 20px;
  color: #666;
  margin-bottom: 15px;
}

.form {
  margin-top: 50px;
}

.submit-btn {
  margin-top: 30px;
  font-size: 24px;
  width: 100%;
}
</style>
