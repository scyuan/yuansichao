<template>
  <div class="about">
    <div class="content">
      <div class="avatar"></div>
      <p class="a-desc">袁斯超</p>
      <p class="a-desc">男</p>
      <p class="a-desc">25</p>
    </div>
  </div>
</template>
<script>
export default {};
</script>
<style lang="scss" scoped>
.content {
  max-width: 800px;
  width: 100%;
  margin: 0 auto;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
  padding: 60px 0;
}
.avatar {
  width: 100px;
  height: 100px;
  background: url("../assets/me.jpeg") no-repeat center;
  background-size: 100% 100%;
  border-radius: 50px;
}
</style>
