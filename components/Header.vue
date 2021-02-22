<template>
  <div class="move">
    <nuxt-link to="/move/in_theaters" tag="div">正在热映</nuxt-link>
    <nuxt-link to="/move/coming_soon" tag="div">即将上映</nuxt-link>
    <nuxt-link to="/move/top250" tag="div">top250</nuxt-link>
  </div>
</template>
<script>
export default {};
</script>
<style scoped>
.move {
  display: flex;
  align-items: center;
  text-align: center;
  width: 100%;
  height: 50px;
  line-height: 50px;
  background-color: black;
}
.move div {
  flex: 1;
  cursor: pointer;
  color: white;
}
.move div:hover {
  color: red;
}
</style>
