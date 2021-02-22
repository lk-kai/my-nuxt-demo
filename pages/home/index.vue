<template>
  <div>
    这是home页面
    <!-- 跳转方式一 -->
    <button @click="next">跳转到首页</button>
    <!-- 跳转方式二 -->
    <nuxt-link to="/">跳转到首页</nuxt-link>
  </div>
</template>
<script>
export default {
  methods: {
    next() {
      this.$router.push("/");
    }
  }
};
</script>
<style lang="" scoped></style>
