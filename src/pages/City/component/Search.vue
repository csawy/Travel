<template>
  <div>
    <div class="search">
      <input class="search-input" v-model="keyword" type="text" placeholder="请输入城市名称或拼音" />
    </div>
    <div class="search-content" ref="search" v-show="keyword">
      <ul>
        <li class="search-item border-bottom" v-for="item of list" :key="item.id" @click="handleCityClick(item.name)">{{
          item.name }}</li>
        <li class="search-item border-bottom" v-show="hasNoData">没有找到匹配数据</li>
      </ul>
    </div>
  </div>
</template>

<script>
import Bscroll from 'better-scroll'
import { mapMutations } from 'vuex'
export default {
  name: 'CitySearch',
  props: {
    cities: Object
  },
  data() {
    return {
      keyword: '',
      list: []
    }
  },
  methods: {
    handleCityClick(city) {
      this.changeCity(city)
      this.$router.push('/')
    },
    ...mapMutations(['changeCity'])
  },
  watch: {
    keyword() {
      if (this.timer) {
        clearTimeout(this.timer)
      }
      if (!this.keyword) {
        this.list = []
        return
      }
      this.timer = setTimeout(() => {
        const result = []
        for (let i in this.cities) {
          this.cities[i].forEach((value) => {
            if (value.spell.indexOf(this.keyword) > -1 || value.name.indexOf(this.keyword) > -1) {
              result.push(value)
            }
          })
        }
        this.list = result
      }, 100)
    }
  },
  updated() {
    this.scroll && this.scroll.refresh()
  },
  computed: {
    hasNoData() {
      return !this.list.length
    }
  },
  mounted() {
    this.scroll = new Bscroll(this.$refs.search)
    this.$nextTick(() => {
      let bscrollDom = this.$refs.search
      this.scroll = new Bscroll(bscrollDom, {
        mouseWheel: true, click: true, tap: true
      })
    })
  }
}
</script>

<style lang="less" scoped>
.search {
  height: .72rem;
  padding: 0 .1rem;
  background: #00bcd4;

  .search-input {
    box-sizing: border-box;
    width: 100%;
    height: .62rem;
    line-height: .62rem;
    text-align: center;
    padding: 0 .1rem;
    border-radius: .06rem;
    color: #666;
  }
}

.search-content {
  z-index: 1;
  overflow: hidden;
  position: absolute;
  top: 1.58rem;
  left: 0;
  right: 0;
  bottom: 0;
  background: #eee;

  .search-item {
    line-height: .62rem;
    padding-left: .2rem;
    background: #fff;
    color: #666;
  }
}
</style>
