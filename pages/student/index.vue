<template>
  <div>
    <h3>这是学生列表页</h3>
    <ul>
      <li v-for="item in stuList" :key="item.id" @click="next(item.id)">
        姓名:{{ item.name }} ---- id:{{ item.id }}
      </li>
    </ul>
    <el-button type="primary">测试button</el-button>
  </div>
</template>
<script>
import axios from "axios";
export default {
  // 在nuxt中 只有created beforecreate这两个钩子函数能正常使用
  // 异步请求不能在created中执行 应在asyncData中使用 这个函数不能使用this
  created() {},
  asyncData(context, callback) {
    axios.get("http://localhost:3301/in_theaters").then(res => {
      console.log(res.data);
      callback(null, { movelist: res.data });
    });
  },
  layout: "header",
  data() {
    return {
      stuList: [
        { name: "张三", id: 1 },
        { name: "李四", id: 2 },
        { name: "王五", id: 3 }
      ]
    };
  },
  methods: {
    next(id) {
      this.$router.push(`/student/${id}`);
    }
  }
};
</script>
<style>
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
