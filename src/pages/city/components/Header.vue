<template>

  <div class="header">
    城市选择
    <router-link to='/'>
      <div class="iconfont back-icon">&#xe624;</div>
    </router-link>
  </div>
</template>
<script>
export default {
  name: 'CityHeader'
}
</script>
<style lang="stylus" scoped>
@import '~@/assets/styles/varibles.styl'
.header
  background-color $bgColor
  height 0.86rem
  line-height 0.86rem
  text-align center
  color #fff
  font-size 0.35rem
  .back-icon
    width 0.64rem
    float left
    text-align center
    color #fff
</style>
