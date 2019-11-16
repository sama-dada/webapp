<template>
  <div class="search">
    <input class="search-input"
           type="text"
           placeholder="输入城市名">
  </div>
</template>
<script>
export default {
  name: 'CitySearch'
}
</script>
<style lang="stylus" scoped>
@import '~@/assets/styles/varibles.styl'
.search
  height 0.72rem
  padding 0 0.1rem
  background-color $bgColor
  .search-input
    box-sizing border-box
    width 100%
    line-height 0.62rem
    text-align center
    padding 0 0.1rem
    color #666
</style>
