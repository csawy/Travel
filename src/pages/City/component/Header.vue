<template>
  <div class="header">
    <router-link to="/">
      <div class="iconfont header-back">&#xe624;</div>
    </router-link>
    境内城市
  </div>
</template>

<script>
export default {
  name: 'CityHeader'
}
</script>

<style lang="less" scoped>
.header {
  position: relative;
  overflow: hidden;
  height: .86rem;
  line-height: .86rem;
  color: #fff;
  text-align: center;
  background: #00bcd4;
  font-size: .32rem;

  .header-back {
    position: absolute;
    top: 0;
    left: 0;
    width: .64rem;
    text-align: center;
    font-size: .4rem;
    color: #fff;
  }
}
</style>
