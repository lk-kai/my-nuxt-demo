<template>
  <div>
    <ul>
      <li v-for="item in movelist" :key="item.id">
        title:{{ item.title }} ---- id:{{ item.id }}
      </li>
    </ul>
  </div>
</template>

<script>
import axios from "../plugins/axios";

export default {
  // 在nuxt中 只有created beforecreate这两个钩子函数能正常使用
  // 异步请求不能在created中执行 应在asyncData中使用 这个函数不能使用this
  created() {},
  beforeCreate() {
    // this.$router.push('/move')
  },
  async asyncData({ redirect }) {
    redirect("/move");
    const { data } = await axios.get("/in_theaters");
    return { movelist: data };
  },
  data() {
    return {
      movelist: []
    };
  }
};
</script>
<style scoped>
ul {
  overflow: hidden;
  list-style: none;
  margin: 0;
  padding: 0;
}
ul li {
  margin: 10px;
  padding-left: 5px;
  border: 1px solid red;
  border-radius: 5px;
}
</style>
