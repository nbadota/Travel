<template>
    <div class="list" ref="wrapper">
      <div>
        <div class="area">
          <div class="title border-topbottom">当前城市</div>
          <div class="button-list">
            <div class="button-wrapper">
              <div class="button">北京</div>
            </div>
          </div>
        </div>
        <div class="area">
          <div class="title border-topbottom">热门城市</div>
          <div class="button-list">
            <div class="button-wrapper" v-for="item of hot" :key="item.id">
              <div class="button">{{item.name}}</div>
            </div>
          </div>
        </div>
        <div class="area" v-for="(item, key) of cities" :key="key">
          <div class="title border-topbottom">{{key}}</div>
          <div class="item-list">
            <div class="item border-bottom" v-for="innerItem of item"
            :key="innerItem.id">{{innerItem.name}}</div>
          </div>
        </div>
      </div>
    </div>
</template>

<script>
import Bscroll from 'better-scroll';
export default {
  name: 'Citylist',
  props: {
    hot: Array,
    cities: Object
  },
  mounted () {
    this.scroll = new Bscroll(this.$refs.wrapper);
  },
  updated () {
    this.scroll.refresh();
  }
};
</script>

<style scoped>
.title {
  padding-left: .2rem;
  line-height: .54rem;
  font-size: .26rem;
  background: #eee;
}
.list {
  overflow: hidden;
  position: absolute;
  top: 1.58rem;
  left: 0;
  right: 0;
  bottom: 0;
}
.border-topbottom:before {
  border-color: #ccc;
}
.border-topbottom:after {
  border-color: #ccc;
}
.border-bottom:before {
  border-color: #ccc;
}
.button-list {
  overflow: hidden;
  padding: .1rem .6rem .1rem .1rem;
}
.button-wrapper {
  float: left;
  width: 33.33%;
}
.button {
  margin: .1rem;
  padding: .1rem 0;
  text-align: center;
  border: .02rem solid #ccc;
  border-radius: .06rem;
}
.item {
  padding-left: .2rem;
  line-height: .76rem;
}
</style>
