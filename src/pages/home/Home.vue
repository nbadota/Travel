<template>
  <div class="icons">
    <home-header></home-header>
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
import {mapState} from 'vuex';
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
      lastCity: '',
      swiperList: [],
      iconList: [],
      recommendList: [],
      weekendList: []
    };
  },
  computed: {
    ...mapState(['city'])
  },
  methods: {
    getHomeInfo () {
      axios.get('/api/index.json?city=' + this.city).then(this.getHomeInfoSucc);
    },
    getHomeInfoSucc (res) {
      res = res.data;
      if (res.ret && res.data) {
        const data = res.data;
        this.swiperList = data.swiperList;
        this.iconList = data.iconList;
        this.recommendList = data.recommendList;
        this.weekendList = data.weekendList;
      }
    }
  },
  mounted () {
    this.lastCity = this.city;
    this.getHomeInfo();
  },
  // 页面重新显示的时候执行
  activated () {
    if (this.lastCity !== this.city) {
      this.lastCity = this.city;
      this.getHomeInfo();
    }
  }
};
</script>

<style scoped>

</style>
