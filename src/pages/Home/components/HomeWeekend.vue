<template>
  <div>
    <div class="title">周末去哪儿</div>
    <ul>
      <li class="item" v-for="item of list" :key="item.id">
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
  props: {
    list: Array
  }
}
</script>

<style lang="less" scoped>
.title {
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

    .item-img-wrapper {
      overflow: hidden;
      height: 0;
      padding-bottom: 37.09%;
    }
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
