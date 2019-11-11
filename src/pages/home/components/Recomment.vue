<template>
  <div class="HomeRecomment">
    <div class="title">热销榜单</div>
    <ul>
      <li class="items"
          v-for="item of recommented"
          :key="item.id">
        <img class="item-img"
             :src="item.imgUrl">
        <div class="item-info">
          <p class="img-title">{{item.title}}</p>
          <p class="img-desc">{{item.desc}}</p>
          <button class="img-button">查看详情</button>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeRecomment',
  data () {
    return {
      recommented: [{
        id: '0001',
        imgUrl: 'https://imgs.qunarzz.com/sight/p0/1409/19/adca619faaab0898245dc4ec482b5722.jpg_250x250_0fc722c0.jpg',
        title: '故宫',
        desc: '北京市东城区景山前街4号'
      }, {
        id: '0002',
        imgUrl: 'https://imgs.qunarzz.com/sight/p0/1409/19/adca619faaab0898245dc4ec482b5722.jpg_250x250_0fc722c0.jpg',
        title: '故宫',
        desc: '北京市东城区景山前街4号'
      }, {
        id: '0003',
        imgUrl: 'https://imgs.qunarzz.com/sight/p0/1409/19/adca619faaab0898245dc4ec482b5722.jpg_250x250_0fc722c0.jpg',
        title: '故宫',
        desc: '北京市东城区景山前街4号'
      }]
    }
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
      color #ccc
    .img-button
      margin-top 0.16rem
      padding 0 0.1rem
      background-color #ff9300
      color #fff
      line-height 0.4rem
      border-radius 0.06rem
</style>
