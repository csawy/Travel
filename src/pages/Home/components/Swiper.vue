<template>
  <div class="wrapper">
    <swiper :options="swiperOption">
      <swiper-slide v-for="item of swiperList" :key="item.id">
        <img class="swiper-img" :src="item.imgUrl" />
      </swiper-slide>
      <div class="swiper-pagination" slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeSwiper',
  data() {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true
      },
      swiperList: [{
        id: '0001',
        imgUrl: 'https://ad-dapp-osscp.qunarzz.com/ad_dapp_oss_oper/050f44261f005665eab6e39bee7de4d0.jpg'
      },
      {
        id: '0002',
        imgUrl: 'https://ad-dapp-osscp.qunarzz.com/ad_dapp_oss_oper/b72d367a4390b52968f563186e69a84e.jpg'
      }
      ]
    }
  }
}
</script>

<style lang="less" scoped>
.wrapper {
  overflow: hidden;
  width: 100%;
  height: 0;
  padding-bottom: 53%;

  .swiper-img {
    width: 100%;
  }

  /deep/ .swiper-pagination-bullet-active {
    background: #fff !important;
  }
}
</style>
