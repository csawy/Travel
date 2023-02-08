<template>
  <div>
    <CityHeader></CityHeader>
    <CitySearch></CitySearch>
  </div>
</template>

<script>
import CityHeader from './component/Header.vue'
import CitySearch from './component/Search.vue'
export default {
  name: 'City',
  components: {
    CityHeader,
    CitySearch
  }
}
</script>

<style lang="less" scoped>

</style>
