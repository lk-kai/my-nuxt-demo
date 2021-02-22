<template>
  <!-- 这个id对应一个_id 文件夹 -->
  <div>学生id---{{ $route.params.id }}</div>
</template>
<script>
export default {
  // nuxt 使用validate方法进行路由校验 返回一个布尔值
  validate(obj) {
    return /^\d+$/.test(obj.params.id);
  },
  created() {
    console.log(this.$route);
  },
  data() {
    return {};
  }
};
</script>
