<template>
  <div class="wrap">
    <nuxt-link
      :to="`/move/${$route.params.type}/${item.id}`"
      v-for="item in movelist"
      :key="item.id"
      class="box"
    >
      <img :src="item.img" :alt="item.title" />
      <h4>电影名: {{ item.title }}</h4>
      <p>上映评分: {{ item.rating === 0 ? "暂无评分" : item.rating }}</p>
    </nuxt-link>
  </div>
</template>
<script>
import axios from "../../../plugins/axios";
export default {
  layout: "moveheader",
  async asyncData({ params }) {
    const { data } = await axios.get(`/${params.type}`);
    return { movelist: data };
  }
};
</script>
<style scoped>
.wrap {
  display: flex;
  flex-direction: column;
  text-align: center;
  align-items: center;
}
.box {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin: 20px 0;
  padding: 10px 0;
  width: 40%;
  box-shadow: 0 0 10px #bbb;
}
.box:hover {
  box-shadow: rgba(0, 0, 0, 0.3) 0px 19px 60px;
}
</style>
