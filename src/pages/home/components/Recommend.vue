<template>
  <div>
    <div class="recommend-title">热销推荐</div>
    <ul>
      <li class="item border-bottom" v-for="item of recommendList" :key="item.id">
        <img class="item-img" :src="item.imgUrl">
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
          <button class="item-button">查看详情</button>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeRecommend',
  data: function () {
    return {
      recommendList: [{
        id: '0001',
        imgUrl: 'https://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20209/158387fe5376294f3776d01358d6b73b.png',
        title: '主题主题主题主题',
        desc: '简介简介简介简介简介简介简介简介简介简介简介简介简介简介'
      }, {
        id: '0002',
        imgUrl: 'https://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20209/158387fe5376294f3776d01358d6b73b.png',
        title: '主题主题主题主题',
        desc: '简介简介简介简介简介简介简介简介简介简介简介简介简介简介'
      }, {
        id: '0003',
        imgUrl: 'https://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20209/158387fe5376294f3776d01358d6b73b.png',
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
.item {
  overflow: hidden;
  display: flex;
  height: 1.9rem;
  border-bottom: 1px solid #eee;
}
.item-img {
  width: 1.7rem;
  height: 1.7rem;
  padding: .1rem;
}
.item-info {
  flex: 1;
  padding: .1rem;
  min-width: 0;
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
.item-button {
  margin-top: .2rem;
  padding: 0 .2rem;
  border-radius: .06rem;
  background: #ff9300;
  color: #fff;
}
</style>
