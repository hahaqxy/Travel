<template>
  <div class="icons">
    <swiper :options="swiperOptions">
      <swiper-slide v-for="(page, index) in pages" :key="index">
        <div class="icon" v-for="item in page" :key="item.id">
          <div class="icon-img">
            <img class="icon-img-content" :src="item.imgUrl" />
          </div>
          <p class="icon-desc">{{item.desc}}</p>
        </div>
      </swiper-slide>
    </swiper>
  </div>
</template>

<script>
  export default {
    name: "HomeIcons",
    props: {
      iconList: Array
    },
    data: function() {
      return {
        swiperOptions: {
          
        }
      }
    },
    computed: {
      pages: function() {
        const pages = [];
        this.iconList.forEach((item, index) => {
          const page = Math.floor(index / 8);
          if(!pages[page]) {
            pages[page] = [];
          }
          pages[page].push(item);
        })
        return pages
      }
    }
  }
</script>

<style scoped lang="stylus">
  @import '~styles/varibles.styl'
  .icons >>> .swiper-container
    height : 0
    padding-bottom : 50%
  .icons
    margin-top : .1rem
    .icon
      position : relative
      overflow : hidden
      float : left
      width : 25%
      height : 0
      padding-bottom : 25%
      .icon-img
        position : absolute
        top : 0
        left : 0
        right : 0
        bottom : .44rem
        box-sizing : border-box
        padding : .1rem
        .icon-img-content
          height : 100%
          display : block
          margin : 0 auto
      .icon-desc
        position : absolute
        left: 0
        right : 0
        bottom : 0
        line-height : .44rem
        height : .44rem
        text-align : center
        color : $darkTextColor
</style>
