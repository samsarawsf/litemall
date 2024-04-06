<template>
  <div class="user_module">
    <van-cell-group>
      <van-cell icon="dingwei" title="收货地址" to="/user/address" isLink/>
    </van-cell-group>
  </div>
</template>

<script>
export default {
  name: 'user-module'
};
</script>


<style scoped lang="scss">
.user_module {
  background-color: #fff;
}
</style>
