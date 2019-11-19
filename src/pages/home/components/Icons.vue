<template>
  <div class="icons">
    <swiper :options="swiperOption"
            v-if="showswiper">
      <swiper-slide v-for="(page,index) of pages"
                    :key="index">
        <div class="icon"
             v-for="item of page"
             :key="item.id">
          <div class="icon-img">
            <img class="icon-img-content"
                 :src="item.imgUrl">
          </div>
          <p class="img-content">{{item.desc}}</p>
        </div>
      </swiper-slide>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeIcons',
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
    pages () {
      const pages = []
      this.list.forEach((item, index) => {
        const page = Math.floor(index / 8)
        if (!pages[page]) {
          pages[page] = []
        }
        pages[page].push(item)
      })
      return pages
    },
    showswiper () {
      return this.list.length
    }
  }
}
</script>

<style lang="stylus" scoped>
.icons
  overflow hidden
  width 100%
  height 0
  padding-bottom 50%
  .icon
    overflow hidden
    position relative
    width 25%
    height 0
    padding-bottom 25%
    float left
    .icon-img
      position absolute
      top 0
      left 0
      right 0
      bottom 0.44rem
      box-sizing border-box
      padding 0.1rem
      .icon-img-content
        display block
        margin 0 auto
        height 100%
  .img-content
    position absolute
    left 0
    right 0
    bottom 0
    height 0.44rem
    line-height 0.44rem
    text-align center
</style>
