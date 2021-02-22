<template>
  <div class="move">
    <nuxt-link to="/move/in_theaters" class="move-bar">正在热映</nuxt-link>
    <nuxt-link to="/move/coming_soon" class="move-bar">即将上映</nuxt-link>
    <nuxt-link to="/move/top250" class="move-bar">top250</nuxt-link>
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
.move-bar {
  flex: 1;
  cursor: pointer;
  color: white;
}
.move-bar:hover {
  color: red;
}
</style>
