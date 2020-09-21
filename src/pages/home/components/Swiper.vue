<template>
  <div class="wrapper">
    <swiper :options="swiperOptions">
      <swiper-slide>
        图片1
      </swiper-slide>
      <swiper-slide>
        图片2
      </swiper-slide>
    </swiper>
    <div class="swiper-pagination" slot="pagination"></div>
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
  padding-bottom: 31.25%;
  background: #ccc;
}
img {
  width: 100%;
}
</style>
