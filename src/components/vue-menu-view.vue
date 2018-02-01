<template>
  <div class="f28 h aas">
    <ul class="vue-menu-list"
      :style="{
        'transform': 'translateY('+ translateY +')',
        'transition': transition
      }"
      >
      <li v-for="item in arr" :key="item.id">{{ item }}</li>
    </ul>
  </div>
</template>

<script>
export default {
  data () {
    return {
      arr: ['撒地方', '华国锋','几月份', '撒地方'],
      pic: 0,
      translateY: 0,
      flag: 80,
      transition: '',
      transitionTime: 0.4,
      intervalTime: 30
    }
  },
  watch: {
    pic (val) {
      if (this.pic === this.arr.length -1) {
        setTimeout(() => {
          this.transition = ''
          this.pic = 0
        }, this.transitionTime * 1000)
      }
      this.translateY = `-${val * this.flag / 100}rem`
    }
  },
  mounted () {
    setInterval(() => {
      this.transition = `all ${this.transitionTime}s`
      this.pic += 1
    }, this.intervalTime)
  }
}
</script>
<style scoped>
  .aas {
    height: .8rem;
    width: 200px;
    margin: 200px auto;
    background-color: #ccc;
    overflow: hidden;
  }
  .vue-menu-list {
    height: .8rem;
  }
  .vue-menu-list li {
    height: .8rem;
    line-height: .8rem;
    font-size: .32rem;
  }
</style>
