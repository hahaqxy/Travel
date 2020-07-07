<template>
  <div class="header">
    城市选择
    <router-link to="/">
      <div class="iconfont city-back">&#xe624;</div>
    </router-link>
  </div>
</template>

<script>
  export default {
    name: 'CityHeader',
    data() {
      return {

      }
    }
  }
</script>

<style scoped lang="stylus">
  @import '~styles/varibles.styl'
  .header
    position : relative
    overflow : hidden
    height : $headerHeight
    line-height : $headerHeight
    text-align : center
    background : $bgColor
    font-size : .32rem
    color : #fff
    .city-back
      position : absolute
      top : 0
      left : 0
      width : .64rem
      text-align : center
      font-size : .4rem
      color : #fff
</style>
