<template>
    <div class="container" @click="handleGallaryClick">
      <div class="wrapper">
        <swiper :options="swiperOptions">
          <swiper-slide>
            <img class="gallary-img" src="http://img1.qunarzz.com/sight/p0/1409/19/adca619faaab0898245dc4ec482b5722.jpg_140x140_80f63803.jpg">
          </swiper-slide>
          <swiper-slide>
            <img class="gallary-img" src="http://img1.qunarzz.com/sight/p0/1409/19/adca619faaab0898245dc4ec482b5722.jpg_140x140_80f63803.jpg">
          </swiper-slide>
          <div class="swiper-pagination" slot="pagination"></div>
        </swiper>
      </div>
    </div>
</template>

<script>
export default {
  name: 'CommonGallary',
  props: {
    imgs: Array,
    default () {
      return [];
    }
  },
  data () {
    return {
      swiperOptions: {
        pagination: '.swiper-pagination',
        paginationType: 'fraction',
        observer: true,
        observeParents: true
      }
    };
  },
  methods: {
    handleGallaryClick () {
      this.$emit('close');
    }
  }
};
</script>

<style scoped>
.container >>> .swiper-container {
  overflow: inherit;
}
.container {
  display: flex;
  flex-direction: column;
  justify-content: center;
  z-index: 99;
  position: fixed;
  left: 0;
  right: 0;
  top: 0;
  bottom: 0;
  background: #000;
}
.wrapper {
  height: 0;
  width: 100%;
  padding-bottom: 100%;
}
.gallary-img {
  width: 100%;
}
.swiper-pagination {
  color: #fff;
  bottom: -1rem;
}
</style>
