<template>
  <div class="HomeRecomment">
    <div class="title">周末去哪儿</div>
    <ul>
      <li class="items"
          v-for="item of list"
          :key="item.id">
        <div class="img-weapper">
          <img class="item-img"
               :src="item.imgUrl"></div>
        <div class="item-info">
          <p class="img-title">{{item.title}}</p>
          <p class="img-desc">{{item.desc}}</p>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeWeekend',
  props: {
    list: Array
  }
}
</script>

<style lang="stylus" scoped>
.title
  line-height 0.6rem
  background-color #ccc
  text-indent 0.2rem
.items
  .item-img
    overflow hidden
    width 100%
  .item-info
    padding 0.1rem
    .img-desc
      color #ccc
</style>
