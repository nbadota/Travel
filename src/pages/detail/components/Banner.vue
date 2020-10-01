<template>
  <div>
    <div class="banner" @click="handleBannerClick">
      <img class="banner-img" src="//img1.qunarzz.com/sight/p0/1409/19/adca619faaab0898245dc4ec482b5722.jpg_600x330_f922b488.jpg">
      <div class="banner-info">
        <div class="banner-title">biaotibiaoti</div>
        <div class="banner-number"><span class="iconfont banner-icon">&#xe60b;</span>39</div>
      </div>
    </div>
    <common-gallary :imgs="imgs" v-show="showGallary" @close="handleGallaryClose"></common-gallary>
  </div>
</template>

<script>
import CommonGallary from 'common/gallary/Gallary';
export default {
  name: 'DetailBanner',
  data () {
    return {
      imgs: [],
      showGallary: false
    };
  },
  methods: {
    handleBannerClick () {
      this.showGallary = true;
    },
    handleGallaryClose () {
      this.showGallary = false;
    }
  },
  components: {
    CommonGallary
  }
};
</script>

<style scoped>
.banner {
  position: relative;
  overflow: hidden;
  height: 0;
  padding-bottom: 55%;
}
.banner-img {
  width: 100%;
}
.banner-info {
  display: flex;
  position: absolute;
  left: 0;
  right: 0;
  bottom: 0;
  line-height: .6rem;
  color: #fff;
  background-image: linear-gradient(top, rgba(0, 0, 0, 0),rgba(0, 0, 0, 0.8));
}
.banner-title {
  flex: 1;
  font-size: .32rem;
  padding: 0 .2rem;
}
.banner-number {
  height: .32rem;
  padding: 0 .4rem;
  margin-top: .14rem;
  line-height: .32rem;
  border-radius: .2rem;
  font-size: .24rem;
  background: rgba(0, 0, 0, .6);
}
.banner-icon{
  font-size: .24rem;
}
</style>
