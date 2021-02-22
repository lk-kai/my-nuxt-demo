<template>
  <div>
    <h3>这是学生列表页</h3>
    <ul>
      <li v-for="item in stuList" :key="item.id" @click="next(item.id)">
        姓名:{{ item.name }} ---- id:{{ item.id }}
      </li>
    </ul>
  </div>
</template>
<script>
export default {
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
