<template>
  <div class="container"
       @click="handleBannerclose">
    <div class="wrapper">
      <swiper :options="swiperOption">
        <swiper-slide v-for="(item, index) in imgs"
                      :key="index">
          <img class="swiper-img"
               :src="item" />
        </swiper-slide>
        <div class="swiper-pagination"
             slot="pagination"></div>
      </swiper>
    </div>
  </div>
</template>
<script>
export default {
  name: 'Gallary',
  props: {
    imgs: {
      type: Array,
      default () {
        return []
      }
    }
  },
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        paginationType: 'fraction',
        observeParents: true,
        observer: true
      }
    }
  },
  methods: {
    handleBannerclose () {
      this.$emit('close')
    }
  }
}
</script>
<style lang="stylus" scoped>
.container
  z-index 99
  position fixed
  display flex
  flex-direction column
  justify-content center
  top 0
  right 0
  bottom 0
  left 0
  background #000
  .wrapper
    color #fff
    .swiper-img
      width 100%
</style>
