<template>
  <div>
    <Header></Header>
    <!-- 占位符 凡是用到这个布局组件的页面,它们的组件都会放在这个坑里面 -->
    <nuxt />
  </div>
</template>
<script>
import Header from "../components/Header";
export default {
  components: {
    Header
  }
};
</script>
