<template>
  <div class="HomeRecomment">
    <div class="title">热销榜单</div>
    <ul>
      <router-link class="items"
                   v-for="item of list"
                   :key="item.id"
                   :to="'/detail/' + item.id">
        <img class="item-img"
             :src="item.imgUrl">
        <div class="item-info">
          <p class="img-title">{{item.title}}</p>
          <p class="img-desc">{{item.desc}}</p>
          <button class="img-button">查看详情</button>
        </div>
      </router-link>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeRecomment',
  props: {
    list: Array
  }
}
</script>

<style lang="stylus" scoped>
.title
  margin-top 0.2rem
  line-height 0.6rem
  background-color #ccc
  text-indent 0.2rem
.items
  display flex
  .item-img
    width 1.7rem
    height 1.7rem
    padding 0.1rem
  .item-info
    flex 1
    padding 0.1rem
    .img-desc
      margin-top 0.1rem
      color #ccc
    .img-button
      margin-top 0.26rem
      padding 0 0.1rem
      background-color #ff9300
      color #fff
      line-height 0.4rem
      border-radius 0.06rem
</style>
