<template>
  <div class="wrapper">
    <swiper :options="swiperOptions">
      <swiper-slide>
        <img src="https://imgs.qunarzz.com/sight/source/1811/f3/86173f863bef61.jpg_r_640x214_52b003ac.jpg">
      </swiper-slide>
      <swiper-slide>
        <img src="https://imgs.qunarzz.com/sight/source/1811/f3/86173f863bef61.jpg_r_640x214_52b003ac.jpg">
      </swiper-slide>
      <div class="swiper-pagination" slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeSwiper',
  data: function () {
    return {
      swiperOptions: {
        pagination: '.swiper-pagination',
        loop: true
      }
    };
  }
};
</script>

<style scoped>
.wrapper >>> .swiper-pagination-bullet-active {
  background: #fff;
}
.wrapper {
  overflow: hidden;
  width: 100%;
  height: 0;
  padding-bottom: 33.9%;
  background: #ccc;
}
img {
  width: 100%;
}
</style>
