<template>
  <div>
    <div class="banner"
         @click="handleBannerclick()">
      <img class="banner-img"
           :src="bannerImg">
      <div class="banner-info">
        <div class="banner-title">{{this.sightName}}</div>
        <div class="banner-number"><span class="iconfont banner-icon">&#xe608;</span>{{this.gallaryImgs.length}}</div>
      </div>
    </div>
    <common-gallary :imgs="gallaryImgs"
                    v-show="GallaryShow"
                    @close="handleBannerclose"></common-gallary>
  </div>
</template>
<script>
import CommonGallary from 'common/gallary/Gallary'
export default {
  name: 'DetailBanner',
  props: {
    sightName: String,
    bannerImg: String,
    gallaryImgs: Array
  },
  data () {
    return {
      GallaryShow: false
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
