<template>
  <div class="wrapper">
    <swiper :options="swiperOptions" v-if="showSwiper">
        <swiper-slide v-for="item in swiperList" :key="item.id">
          <img class="swiper-img" :src="item.imgUrl" />
        </swiper-slide>
        <div class="swiper-pagination" slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
  export default {
    name: "HomeSwiper",
    props: {
      swiperList: Array
    },
    data: function() {
      return {
        swiperOptions: {
          pagination: '.swiper-pagination',
          loop: true
        }
      }
    },
    computed: {
      showSwiper() {
        return this.swiperList.length;
      }
    }
  }
</script>

<style scoped lang="stylus">
  .wrapper >>> .swiper-pagination-bullet-active
    background-color : #fff
  .wrapper
    width : 100%
    height : 0
    overflow : hidden
    padding-bottom : 31.25%
    background-color : #eee
    .swiper-img
      width : 100%
</style>
