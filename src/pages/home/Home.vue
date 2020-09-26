<template>
  <div class="icons">
    <home-header :city="city"></home-header>
    <home-swiper :list="swiperList"></home-swiper>
    <home-icons  :list="iconList"></home-icons>
    <home-rcommend  :list="recommendList"></home-rcommend>
    <home-weekend :list="weekendList"></home-weekend>
  </div>
</template>

<script>
import HomeHeader from './components/Header';
import HomeSwiper from './components/Swiper';
import HomeIcons from './components/Icons';
import HomeRcommend from './components/Recommend';
import HomeWeekend from './components/Weekend';
import axios from 'axios';
export default {
  name: 'Home.vue',
  components: {
    HomeHeader,
    HomeSwiper,
    HomeIcons,
    HomeRcommend,
    HomeWeekend
  },
  data: function () {
    return {
      city: '',
      swiperList: [],
      iconList: [],
      recommendList: [],
      weekendList: []
    };
  },
  methods: {
    getHomeInfo () {
      axios.get('/api/index.json').then(this.getHomeInfoSucc);
    },
    getHomeInfoSucc (res) {
      res = res.data;
      if (res.ret && res.data) {
        const data = res.data;
        this.city = data.city;
        this.swiperList = data.swiperList;
        this.iconList = data.iconList;
        this.recommendList = data.recommendList;
        this.weekendList = data.weekendList;
      }
    }
  },
  mounted () {
    this.getHomeInfo();
  }
};
</script>

<style scoped>

</style>
