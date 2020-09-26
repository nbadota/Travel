<template>
  <div class="wrapper">
    <swiper :options="swiperOptions" v-if="list.length">
      <swiper-slide v-for="item of list" :key="item.id">
        <img :src="item.imgUrl">
      </swiper-slide>
      <div class="swiper-pagination" slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeSwiper',
  props: {
    list: Array
  },
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
