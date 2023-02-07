<template>
  <div>
    <div class="title">周末去哪儿</div>
    <ul>
      <li class="item" v-for="item of HomeWeekendList" :key="item.id">
        <img class="item-img" :src="item.imgUrl" />
        <div class="item-info">
          <p class="item-title">{{ item.title }}</p>
          <p class="item-desc">{{ item.desc }}</p>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeWeekend',
  data() {
    return {
      HomeWeekendList: [{
        id: '0001',
        imgUrl: 'https://tr-osdcp.qunarzz.com/tr-osd-tr-manager/img/c06304f3eb91aa6bca56c1f88dff7986.jpg',
        title: '成都小长假周末必玩榜',
        desc: '成都旅游该去哪儿？怎样玩得舒心、避坑？相信这是大家最关心的问题了。今天我就来推荐几个景点~'
      },
      {
        id: '0002',
        imgUrl: 'https://tr-osdcp.qunarzz.com/tr-osd-tr-manager/img/086174eabf6bd34955ce7b76fb8be567.jpg',
        title: '上海小长假周末必玩榜',
        desc: '上海既有现代化的建筑，又有老上海的市井气息，有小资文艺的时尚艺术，也有江南水乡的柔情似水初来乍到~'
      }, {
        id: '0003',
        imgUrl: 'https://tr-osdcp.qunarzz.com/tr-osd-tr-manager/img/09da45332823f014429b94e55fa96c5d.jpg',
        title: '北京小长假周末必玩榜',
        desc: '每到小长假或者周末面对北京如此多的景点该如何做选择呢？快来看看推荐吧！'
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

  .item-img {
    width: 100%;
    height: 130px;
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
  }
}
</style>
