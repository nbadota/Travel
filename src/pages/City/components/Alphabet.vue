<template>
    <ul class="list">
      <li class="item" v-for="item of letters" :key="item" :ref="item"
      @click="handleLetterClick" @touchstart="handleTouchStart"
      @touchmove="handleTouchMove" @touchend="handleTouchEnd">{{item}}</li>
    </ul>
</template>

<script>
export default {
  name: 'CityAlphabet',
  props: {
    cities: Object
  },
  computed: {
    letters () {
      const letters = [];
      for (let i in this.cities) {
        letters.push(i);
      }
      return letters;
    }
  },
  data: function () {
    return {
      touchStatus: false,
      timer: null,
      lastTime: null
    };
  },
  updated () {
    this.startY = this.$refs['A'][0].offsetTop;
  },
  methods: {
    handleLetterClick (e) {
      this.$emit('change', e.target.innerText);
    },
    handleTouchStart () {
      this.touchStatus = true;
    },
    handleTouchMove (e) {
      // 节流
      if (this.touchStatus) {
        let now = +new Date();
        if (this.lastTime && this.lastTime - now < 8) {
          clearTimeout(this.timer);
        }
        this.timer = setTimeout(() => {
          const touchY = e.touches[0].clientY - 79;
          const index = Math.floor((touchY - this.startY) / 20);
          if (index >= 0 && index < this.letters.length) {
            this.$emit('change', this.letters[index]);
          }
          this.lastTime = +new Date();
        }, 8);
      }
    },
    handleTouchEnd () {
      this.touchStatus = false;
    }
  }
};
</script>

<style scoped>
.list {
  display: flex;
  flex-direction: column;
  justify-content: center;
  position: absolute;
  top: 1.58rem;
  right: 0;
  bottom: 0;
  width: .4rem;
}
.item {
  text-align: center;
  line-height: .4rem;
  color: #00bcd4;
}
</style>
