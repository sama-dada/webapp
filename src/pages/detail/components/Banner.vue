<template>
  <div>
    <div class="banner"
         @click="handleBannerclick()">
      <img class="banner-img"
           src="//img1.qunarzz.com/sight/p0/1910/7f/7f5c25e01d156624a3.water.jpg_600x330_8746f289.jpg">
      <div class="banner-info">
        <div class="banner-title">南昌融创海世界</div>
        <div class="banner-number"><span class="iconfont banner-icon">&#xe608;</span>31</div>
      </div>
    </div>
    <common-gallary :imgs="imgs"
                    v-show="GallaryShow"
                    @close="handleBannerclose"></common-gallary>
  </div>
</template>
<script>
import CommonGallary from 'common/gallary/Gallary'
export default {
  name: 'DetailBanner',
  data () {
    return {
      GallaryShow: false,
      imgs: ['http://img1.qunarzz.com/sight/p0/1910/7f/7f5c25e01d156624a3.water.jpg_600x330_8746f289.jpg',
        'http://img1.qunarzz.com/sight/p0/1703/84/84f8cd4e58c3032aa3.img.jpg_350x240_c76a8bd9.jpg']
    }
  },
  methods: {
    handleBannerclick () {
      this.GallaryShow = true
    },
    handleBannerclose () {
      this.GallaryShow = false
    }
  },
  components: {
    CommonGallary
  }
}
</script>
<style lang="stylus" scoped>
.banner
  position relative
  overflow hidden
  height 0
  padding-bottom 55%
  .banner-img
    width 100%
  .banner-info
    position absolute
    display flex
    left 0
    right 0
    bottom 0
    height 0.4rem
    line-height 0.4rem
    color #fff
    background-image linear-gradient(top, rgba(0, 0, 0, 0), rgba(0, 0, 0, 0.8))
    .banner-title
      padding 0 0.2rem 0.2rem 0.2rem
      flex 1
    .banner-number
      padding 0 0.4rem
      height 0.32rem
      line-height 0.32rem
      border-radius 0.2rem
      .banner-icon
        font-size 0.24rem
</style>
