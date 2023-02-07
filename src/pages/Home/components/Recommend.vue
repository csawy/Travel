<template>
  <div>
    <div class="title">热销推荐</div>
    <ul>
      <li class="item" v-for="item of recommendList" :key="item.id">
        <img class="item-img" :src="item.imgUrl" />
        <div class="item-info">
          <p class="item-title">{{ item.title }}</p>
          <p class="item-desc">{{ item.desc }}</p>
          <button class="item-button">查看详情</button>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeRecommend',
  data() {
    return {
      recommendList: [{
        id: '0001',
        imgUrl: 'https://imgs.qunarzz.com/p/tts2/1804/59/deb858a64b1b8402.jpg_r_390x260x95_d04c34ec.jpg',
        title: '【跟团游】寒假特惠 华山1日游',
        desc: '含自加热营养餐/海底捞自加热米饭/低脂餐任选一+索道+进山车+登山手套+祈福带'
      },
      {
        id: '0002',
        imgUrl: '	https://image.maigoo.com/upload/images/20181219/09152652104_640x426.jpg',
        title: '【跟团游】泰国曼谷+芭提雅6日跟团游|大皇宫游湄南河',
        desc: '专车接送您往返曼谷机场与酒店之间,全程豪华旅游空调车'
      }, {
        id: '0003',
        imgUrl: 'https://imgs.qunarzz.com/p/tts2/1804/59/deb858a64b1b8402.jpg_r_390x260x95_d04c34ec.jpg',
        title: '【跟团游】寒假特惠 华山1日游',
        desc: '含自加热营养餐/海底捞自加热米饭/低脂餐任选一+索道+进山车+登山手套+祈福带'
      }, {
        id: '0004',
        imgUrl: '	https://image.maigoo.com/upload/images/20181219/09152652104_640x426.jpg',
        title: '【跟团游】泰国曼谷+芭提雅6日跟团游|大皇宫游湄南河',
        desc: '专车接送您往返曼谷机场与酒店之间,全程豪华旅游空调车'
      }, {
        id: '0005',
        imgUrl: 'https://imgs.qunarzz.com/p/tts2/1804/59/deb858a64b1b8402.jpg_r_390x260x95_d04c34ec.jpg',
        title: '【跟团游】寒假特惠 华山1日游',
        desc: '含自加热营养餐/海底捞自加热米饭/低脂餐任选一+索道+进山车+登山手套+祈福带'
      }
      ]
    }
  }
}
</script>

<style lang="less" scoped>
.title {
  margin-top: .2rem;
  line-height: .8rem;
  background: #eee;
  text-align: .2rem;
  padding-left: .2rem;
  font-size: 16px;
}

.item {
  display: flex;
  height: 1.9rem;
  overflow: hidden;

  .item-img {
    width: 1.7rem;
    height: 1.7rem;
    padding: .1rem;
  }

  .item-info {
    flex: 1;
    padding: .1rem;
    min-width: 0;

    .item-title {
      line-height: .54rem;
      font-size: .32rem;
      overflow: hidden;
      white-space: nowrap;
      text-overflow: ellipsis;
    }

    .item-desc {
      line-height: .4rem;
      color: #ccc;
      overflow: hidden;
      white-space: nowrap;
      text-overflow: ellipsis;
    }

    .item-button {
      line-height: .40rem;
      background: #ff9300;
      padding: 0 .2rem;
      border-radius: .06rem;
      color: #fff;
    }
  }
}
</style>
