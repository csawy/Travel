<template>
  <div class="icons">
    <swiper>
      <swiper-slide v-for="(page, index) of pages" :key="index">
        <div class="icon" v-for="item of page" :key="item.id">
          <div class="icon-img">
            <img class="icon-img-content" :src="item.imgUrl" />
          </div>
          <p class="icon-desc">{{ item.desc }}</p>
        </div>
      </swiper-slide>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeIcons',
  props: {
    list: Array
  },
  data() {
    return {
      iconList: [
        {
          id: '0001',
          imgUrl: 'https://s.qunarzz.com/homenode/images/touchheader/hotel.png',
          desc: '酒店民宿'
        }, {
          id: '0002',
          imgUrl: 'https://s.qunarzz.com/homenode/images/touchheader/flight.png',
          desc: '机票订购'
        }, {
          id: '0003',
          imgUrl: 'https://s.qunarzz.com/homenode/images/touchheader/train.png',
          desc: '火车票订购'
        }, {
          id: '0004',
          imgUrl: 'https://s.qunarzz.com/homenode/images/touchheader/package.png',
          desc: '热门景点'
        }, {
          id: '0005',
          imgUrl: 'https://s.qunarzz.com/homenode/images/touchheader/piao.png',
          desc: '周边游'
        },
        {
          id: '0006',
          imgUrl: 'https://s.qunarzz.com/homenode/images/touchheader/hotel.png',
          desc: '酒店民宿'
        }, {
          id: '0007',
          imgUrl: 'https://s.qunarzz.com/homenode/images/touchheader/flight.png',
          desc: '机票订购'
        }, {
          id: '0008',
          imgUrl: 'https://s.qunarzz.com/homenode/images/touchheader/train.png',
          desc: '火车票订购'
        }, {
          id: '0009',
          imgUrl: 'https://s.qunarzz.com/homenode/images/touchheader/package.png',
          desc: '热门景点'
        }, {
          id: '0010',
          imgUrl: 'https://s.qunarzz.com/homenode/images/touchheader/piao.png',
          desc: '周边游'
        }
      ]
    }
  },
  computed: {
    pages() {
      const pages = []
      this.iconList.forEach((item, index) => {
        const page = Math.floor(index / 8)
        if (!pages[page]) {
          pages[page] = []
        }
        pages[page].push(item)
      })
      return pages
    }
  }
}
</script>

<style lang="less" scoped>
.icons {
  overflow: hidden;
  height: 0;
  padding-bottom: 50%;

  .icon {
    position: relative;
    overflow: hidden;
    float: left;
    width: 25%;
    height: 0;
    padding-bottom: 25%;

    .icon-img {
      position: absolute;
      top: 0;
      left: 0;
      right: 0;
      bottom: .55rem;

      .icon-img-content {
        display: block;
        height: 100%;
        margin: 0 auto;
      }
    }

    .icon-desc {
      position: absolute;
      left: 0;
      right: 0;
      bottom: 0;
      height: .44rem;
      line-height: .44rem;
      text-align: center;
      overflow: hidden;
      white-space: nowrap;
      text-overflow: ellipsis;
    }
  }

  /deep/.swiper-container {
    height: 0;
    padding-bottom: 50%;
  }
}
</style>
