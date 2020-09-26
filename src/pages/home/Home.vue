<template>
  <div class="icons">
    <home-header></home-header>
    <home-swiper></home-swiper>
    <home-icons></home-icons>
    <home-rcommend></home-rcommend>
    <home-weekend></home-weekend>
  </div>
</template>

<script>
import HomeHeader from './components/Header';
import HomeSwiper from './components/Swiper';
import HomeIcons from './components/Icons';
import HomeRcommend from './components/Recommend';
import HomeWeekend from './components/Weekend';
export default {
  name: 'Home.vue',
  components: {
    HomeHeader,
    HomeSwiper,
    HomeIcons,
    HomeRcommend,
    HomeWeekend
  }
};
</script>

<style scoped>

</style>
