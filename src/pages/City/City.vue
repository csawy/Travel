<template>
  <div>
    <CityHeader></CityHeader>
    <CitySearch></CitySearch>
    <CityList></CityList>
    <CityAlphabet></CityAlphabet>
  </div>
</template>

<script>
import CityHeader from './component/Header.vue'
import CitySearch from './component/Search.vue'
import CityList from './component/List.vue'
import CityAlphabet from './component/Alphabet.vue'
export default {
  name: 'City',
  components: {
    CityHeader,
    CitySearch,
    CityList,
    CityAlphabet
  }
}
</script>

<style lang="less" scoped>

</style>
