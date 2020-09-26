<template>
  <div class="header">
    <div class="header-left">
      <div class="iconfont back-icon">&#xe624;</div>
    </div>
    <div class="header-input">
      <span class="iconfont">&#xe632;</span>
    </div>
    <div class="header-right">
      {{this.city}}
      <span class="iconfont arrow-icon">&#xe64a;</span>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HomeHeader',
  props: {
    city: String
  }
};
</script>

<style scoped>
.header {
  display: flex;
  height: .86rem;
  line-height: .86rem;
  background: #00bcd4;
  color: #fff;
}
.header-left {
  width: .64rem;
  float: left;
}
.back-icon {
  text-align: center;
  font-size: .4rem;
}
.header-input {
  flex: 1;
  height: .64rem;
  line-height: .64rem;
  margin-left: .2rem;
  margin-top: .12rem;
  padding-left: .2rem;
  border-radius: .1rem;
  background: #fff;
  color: #ccc;
}
.header-right {
  width: 1.24rem;
  float: right;
  text-align: center;
}
.arrow-icon {
  font-size: .24rem;
}
</style>
