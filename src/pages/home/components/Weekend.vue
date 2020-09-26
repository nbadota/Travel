<template>
  <div>
    <div class="recommend-title">周末去哪儿</div>
    <ul>
      <li class="item border-bottom" v-for="item of recommendList" :key="item.id">
        <div class="item-img-wrapper">
          <img class="item-img" :src="item.imgUrl">
        </div>
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeWeekend',
  data: function () {
    return {
      recommendList: [{
        id: '0001',
        imgUrl: 'https://imgs.qunarzz.com/sight/source/1811/f3/86173f863bef61.jpg_r_640x214_52b003ac.jpg',
        title: '主题主题主题主题',
        desc: '简介简介简介简介简介简介简介简介简介简介简介简介简介简介'
      }, {
        id: '0002',
        imgUrl: 'https://imgs.qunarzz.com/sight/source/1811/f3/86173f863bef61.jpg_r_640x214_52b003ac.jpg',
        title: '主题主题主题主题',
        desc: '简介简介简介简介简介简介简介简介简介简介简介简介简介简介'
      }, {
        id: '0003',
        imgUrl: 'https://imgs.qunarzz.com/sight/source/1811/f3/86173f863bef61.jpg_r_640x214_52b003ac.jpg',
        title: '主题主题主题主题',
        desc: '简介简介简介简介简介简介简介简介简介简介简介简介简介简介'
      }]
    };
  }
};
</script>

<style scoped>
  .recommend-title {
    margin-top: .2rem;
    line-height: .8rem;
    background: #eee;
    text-indent: .2rem;
  }
  .item-img-wrapper {
    overflow: hidden;
    height: 0;
    padding-bottom: 33.9%;
  }
  .item-img {
   width: 100%;
  }
  .item-info {
    padding: .1rem;
  }
  .item-title {
    overflow: hidden;
    line-height: .54rem;
    font-size: .32rem;
    white-space: nowrap;
    text-overflow: ellipsis;
  }
  .item-desc {
    overflow: hidden;
    line-height: .4rem;
    white-space: nowrap;
    text-overflow: ellipsis;
    color: #bbb;
  }
</style>
