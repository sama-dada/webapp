<template>
  <div class="list"
       ref="wrapper">
    <div>
      <div class="area ">
        <div class="title border-topbottom">当前城市</div>
        <div class="button-list">
          <div class="button-wapper">
            <div class="button">{{this.$store.state.city}}</div>
          </div>
        </div>
      </div>
      <div class="area">
        <div class="title border-topbottom">热门城市</div>
        <div class="button-list">
          <div class="button-wapper"
               v-for="item of hot"
               :key="item.id"
               @click="handleCityClick(item.name)">
            <div class="button">{{item.name}}</div>
          </div>
        </div>
      </div>
      <div class="area"
           v-for="(item, key) of cities"
           :key="key">
        <div class="title border-topbottom">{{key}}</div>
        <div class="item">
          <div class="item-list border-bottom"
               v-for="innerItem of item"
               :key="innerItem.id"
               @click="handleCityClick(innerItem.name)">{{innerItem.name}}</div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import Bescroll from 'better-scroll'
export default {
  name: 'CityList',
  props: {
    cities: Object,
    hot: Array
  },
  methods: {
    handleCityClick (city) {
      this.$store.commit('changeCity', city) // dispatch
      this.$router.push('/')
    }
  },
  mounted () {
    this.scroll = new Bescroll(this.$refs.wrapper)
  }
}
</script>
<style lang="stylus" scoped>
@import '~@/assets/styles/varibles.styl'
.border-bottom
  &:before
    border-color #ccc
.border-topbottom
  &:before
    border-color #ccc
  &:after
    border-color #ccc
.list
  overflow hidden
  position absolute
  top 1.58rem
  left 0
  right 0
  bottom 0
  .title
    line-height 0.54rem
    background-color #eee
    padding-left 0.2rem
    font-size 0.26rem
  .button-list
    overflow hidden
    padding 0.1rem 0.6rem 0.1rem 0.1rem
    .button-wapper
      width 33.3%
      float left
      .button
        padding 0.1rem
        margin 0.1rem
        text-align center
        border 0.02rem solid #ccc
        border-radius 0.06rem
  .item
    line-height 0.64rem
    padding-left 0.2rem
</style>
