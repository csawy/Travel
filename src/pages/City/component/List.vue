<template>
  <div class="list" ref="wrapper">
    <div>
      <div class="area">
        <div class="title border-topbottom">当前城市</div>
        <div class="button-list">
          <div class="button-wrapper">
            <div class="button">{{ this.currentCity }}</div>
          </div>
        </div>
      </div>
      <div class="area">
        <div class="title border-topbottom">热门城市</div>
        <div class="button-list">
          <div class="button-wrapper" v-for="item of hot" :key="item.id" @click="handleCityClick(item.name)">
            <div class="button">{{ item.name }}</div>
          </div>
        </div>
      </div>
      <div class="area" v-for="(item, key) of cities" :key="key" :ref="key">
        <div class="title border-topbottom">{{ key }}</div>
        <div class="item-list">
          <div class="item border-bottom" v-for="innerItem of item" :key="innerItem.id"
            @click="handleCityClick(innerItem.name)">{{ innerItem.name }}</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Bscroll from 'better-scroll'
import { mapState, mapMutations } from 'vuex'
export default {
  name: 'CityList',
  props: {
    hot: Array,
    cities: Object,
    letter: String
  },
  computed: {
    ...mapState({
      currentCity: 'city'
    })
  },
  methods: {
    handleCityClick(city) {
      this.changeCity(city)
      this.$router.push('/')
    },
    ...mapMutations(['changeCity'])
  },
  updated() {
    this.scroll && this.scroll.refresh()
  },
  watch: {
    letter() {
      if (this.letter) {
        const element = this.$refs[this.letter][0]
        this.scroll.scrollToElement(element)
      }
    }
  },
  mounted() {
    this.scroll = new Bscroll(this.$refs.wrapper, { click: true })
    this.$nextTick(() => {
      let bscrollDom = this.$refs.wrapper
      this.scroll = new Bscroll(bscrollDom, {
        mouseWheel: true, click: true, tap: true
      })
    })
  }
}
</script>

<style lang="less" scoped>
.list {
  overflow: hidden;
  position: absolute;
  top: 1.58rem;
  left: 0;
  bottom: 0;
  right: 0;

  .title {
    line-height: .54rem;
    background: #eee;
    font-size: .26rem;
    padding-left: .2rem;
    color: #666;
  }

  .border-topbottom {
    border-color: #ccc;
  }

  .button-list {
    overflow: hidden; // 触发BFC
    padding: .1rem .6rem .1rem .1rem;

    .button-wrapper {
      float: left;
      width: 33.33%;

      .button {
        margin: .1rem;
        padding: .1rem 0;
        text-align: center;
        border: .02rem solid #ccc;
        border-radius: .06rem;
      }
    }
  }

  .item-list {
    .item {
      line-height: .76rem;
      padding-left: .2rem;
    }
  }
}
</style>
