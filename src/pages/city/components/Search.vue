<template>
  <div>
    <div class="search">
      <input v-model="keyword"
             class="search-input"
             type="text"
             placeholder="输入城市名">
    </div>
    <div class="search-content"
         ref="search"
         v-show="keyword">
      <ul>
        <li class="search-list border-bottom"
            v-for="item of list"
            :key="item.id"
            @click="handleCityClick(item.name)">{{item.name}}</li>
        <li class="search-list border-bottom"
            v-show="hasNoData">没有找到匹配数据</li>
      </ul>
    </div>
  </div>
</template>
<script>
import Bescroll from 'better-scroll'
export default {
  name: 'CitySearch',
  props: {
    cities: Object
  },
  data () {
    return {
      keyword: '',
      list: [],
      timer: null
    }
  },
  methods: {
    handleCityClick (city) {
      this.$store.commit('changeCity', city) // dispatch
      // 页面跳转
      this.$router.push('/')
    }
  },
  // 计算属性
  computed: {
    hasNoData () {
      return !this.list.length
    }
  },
  watch: {
    keyword () {
      if (this.timer) {
        clearTimeout(this.timer)
      }
      if (!this.keyword) {
        this.list = []
        return
      }
      // 对输入框进行监听事件
      this.timer = setTimeout(() => {
        const result = []
        for (let i in this.cities) {
          this.cities[i].forEach((value) => {
            if (value.spell.indexOf(this.keyword) > -1 || value.name.indexOf(this.keyword) > -1) {
              result.push(value)
            }
          })
        }
        this.list = result
      }, 100)
    }
  },
  mounted () {
    this.scroll = new Bescroll(this.$refs.search)
  }
}
</script>
<style lang="stylus" scoped>
@import '~@/assets/styles/varibles.styl'
.search
  height 0.72rem
  padding 0 0.1rem
  background-color $bgColor
  .search-input
    box-sizing border-box
    width 100%
    line-height 0.62rem
    text-align center
    padding 0 0.1rem
    color #666
.search-content
  overflow hidden
  position absolute
  z-index 1
  top 1.58rem
  left 0
  right 0
  bottom 0
  background-color #eee
  .search-list
    background-color #fff
    color #666
    line-height 0.62rem
    padding-left 0.2rem
</style>
