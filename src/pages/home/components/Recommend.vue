<template>
  <div>
    <div class="recommend-title">热销推荐</div>
    <ul>
      <router-link tag="li" :to="'/detail/' + item.id" class="item border-bottom" v-for="item of this.list" :key="item.id">
        <img class="item-img" :src="item.imgUrl">
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
          <button class="item-button">查看详情</button>
        </div>
      </router-link>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeRecommend',
  props: {
    list: Array
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
