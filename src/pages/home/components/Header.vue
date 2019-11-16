<template>
  <div class="header">
    <div class="header-left">
      <div class="iconfont back-icon">&#xe624;</div>
    </div>
    <div class="header-input">
      <span class="iconfont">&#xe632;</span>
      <input class="header-search"
             type="text"
             placeholder="输入景点/城市">
    </div>
    <router-link to='/city'>
      <div class="
             header-right">城市
        <span class="iconfont">&#xe62d;</span>
      </div>
    </router-link>
  </div>
</template>

<script>
export default {
  name: 'HomeHeader'
}
</script>

<style lang="stylus" scoped>
@import '~@/assets/styles/varibles.styl'
.header
  display flex
  line-height 0.86rem
  background-color $bgColor
  color #fff
  .header-left
    width 0.64rem
    float left
    .back-icon
      text-align center
  .header-input
    flex 1
    height 0.64rem
    line-height 0.64rem
    margin-top 0.12rem
    margin-left 0.2rem
    padding-left 0.1rem
    background-color #fff
    color #ccc
    border-radius 0.1rem
    .header-search
      margin-bottom 0.1rem
  .header-right
    width 1.24rem
    float right
    text-align center
    color #fff
</style>
