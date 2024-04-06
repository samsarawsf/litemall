<template>
  <div class="comment-section">
    <div class="comment-rating">
      <div class="rating-label">评分：</div>
      <van-rate
          v-model="star"
          :size="25"
          color="#ffd21e"
          void-icon="coupon"
          void-color="#eee"
          @change="onRateChange"
      />
      <div class="rating-text">{{ starText }}</div>
    </div>
    <div class="comment-input">
      <van-field v-model="comment" label="评价内容" type="textarea" maxlength="140" placeholder="请输入您的评价" />
    </div>
    <div class="comment-upload">
      <van-uploader v-model="fileList" multiple :max-count="3" accept="image/*" :after-read="afterRead" />
    </div>
    <div class="comment-submit">
      <van-button type="primary" @click="submitComment">提交评价</van-button>
    </div>
  </div>
</template>

<script>
import { Rate, Field, Button, Uploader } from 'vant';
import {CommentSave, storageUpload} from '@/api/api';
export default {
  data() {
    return {
      star: 0,
      starText: '',
      comment: '',
      picUrls: [],
      fileList:[]
    };
  },
  methods: {
    afterRead(file){
      const formData = new FormData()
      formData.append('file', file.file);
      storageUpload(formData) .then(res => {
        if (res.data.errno === 0) {
          this.$toast('上传成功');
          this.picUrls.push(res.data.data.url);
          console.log(this.picUrls)
        }
      }).catch(() => {
            this.$toast('上传失败');
      })
      console.log(file);
    },
    onRateChange(value) {
      this.starText = ['很差', '较差', '一般', '很好', '非常满意'][value - 1];
    },
    submitComment() {
      CommentSave({
        valueId: this.$route.params.orderId,
        star: this.star,
        content: this.comment,
        picUrls: this.picUrls,
        hasPicture: this.picUrls.length > 0,
        type: 0
      }).then(res => {
        if (res.data.errno === 0) {
          this.$toast('评价成功');
          this.$router.push({ name: 'home' });
        }
      });
    }
  },
  components: {
    [Rate.name]: Rate,
    [Field.name]: Field,
    [Button.name]: Button,
    [Uploader.name]: Uploader
  }
};
</script>

<style scoped>
.comment-section {
  padding: 20px;
}

.comment-rating {
  display: flex;
  align-items: center;
  margin-bottom: 20px;
}

.rating-label {
  font-size: 18px;
  margin-right: 10px;
  color: #666;
}

.rating-text {
  font-size: 16px;
  color: #666;
}

.comment-input {
  margin-bottom: 20px;
}

.comment-upload {
  margin-bottom: 20px;
}

.comment-submit {
  text-align: center;
}
</style>
