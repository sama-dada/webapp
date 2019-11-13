<template>
  <div class="wapper">
    <swiper :options="swiperOption"
            v-if="showswiper">
      <!-- slides -->
      <swiper-slide v-for="item of list"
                    :key="item.id">
        <img class="swiper-img"
             :src="item.imgUrl" /></swiper-slide>
      <!-- Optional controls -->
      <div class="swiper-pagination"
           slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeSwiper',
  props: {
    list: Array
  },
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true
      }
    }
  },
  computed: {
    showswiper () {
      return this.list.length
    }
  }
}
</script>

<style lang="stylus" scoped>
.wapper>>>.swiper-pagination-bullet-active
  background #fff
.wapper
  width 100%
  .swiper-img
    overflow hidden
    width 100%
</style>
