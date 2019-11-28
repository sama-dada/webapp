<template>
  <div>
    <router-link to='/'
                 class="header-fbs"
                 v-show="showAbs">
      <div class="iconfont back-icon">&#xe624;</div>
    </router-link>
    <div class="header-fixed"
         v-show="!showAbs"
         :style="opacityStyle">
      景点详情
      <router-link to='/'>
        <div class="iconfont fixed-back-icon">&#xe624;</div>
      </router-link>
    </div>
  </div>
</template>
<script>
export default {
  name: 'DetailHeader',
  data () {
    return {
      showAbs: true,
      opacityStyle: {
        opacity: 0
      }
    }
  },
  methods: {
    handleScroll () {
      const top = document.documentElement.scrollTop
      if (top > 60) {
        let opacity = top / 140
        opacity = opacity > 1 ? 1 : opacity
        this.opacityStyle = { opacity }
        this.showAbs = false
      } else {
        this.showAbs = true
      }
    }
  },
  mounted () {
    window.addEventListener('scroll', this.handleScroll)
  },
  unmounted () {
    window.removeEventListener('scroll', this.handleScroll)
  }
}
</script>
<style lang="stylus" scoped>
@import '~@/assets/styles/varibles.styl'
.header-fbs
  position absolute
  left 0.3rem
  top 0.2rem
  width 0.8rem
  height 0.8rem
  border-radius 0.4rem
  .back-icon
    color #fff
.header-fixed
  z-index 2
  position fixed
  top 0
  right 0
  left 0
  height 0.86rem
  line-height 0.86rem
  background-color $bgColor
  text-align center
  color #fff
  font-size 0.35rem
  .fixed-back-icon
    width 0.64rem
    float left
    text-align center
    color #fff
</style>
