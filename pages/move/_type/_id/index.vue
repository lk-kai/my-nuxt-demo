<template>
  <div class="detail">
    <div style="text-align:center">
      <img :src="detail.img" alt="" />
      <h3>{{ detail.title }}</h3>
      <p>电影类型: {{ detail.genres.join(",") }}</p>
      <p>上映时间: {{ detail.details[0].year }}</p>
      <p>详情: {{ detail.details[0].summary }}</p>
    </div>
  </div>
</template>
<script>
import axios from "../../../../plugins/axios";

export default {
  layout: "moveheader",
  async asyncData({ params }) {
    const { data } = await axios.get(
      `/${params.type}/${params.id}?_embed=details`
    );
    console.log(data);
    return { detail: data };
  }
};
</script>
<style scoped>
.detail {
  margin: 10px auto;
  width: 40%;
  padding: 20px;
  box-sizing: border-box;
  box-shadow: 0 0 10px #bbb;
}
</style>
