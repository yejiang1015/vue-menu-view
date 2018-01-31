<template>
  <div class="f28">
    <ul class="vue-menu-list" v-vwidth>
      <li v-for="item in value" :key="item.id">{{ item.name }}</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'vue-menu-view',
  data () {
    current: null
  },
  props: {
    value: {
      type: null,
      default () {
        return [
          {
            name: '撒地方',
            id: ''
          },
          {
            name: '华国锋'
          },
          {
            name: '几月份'
          },
          {
            name: '撒地方'
          },
          {
            name: '华国锋'
          },
          {
            name: '几月份'
          }
        ]
      }
    }
  },
  directives: {
    vwidth: {
      // 指令的定义
      inserted: function (el) {
        el.style.width = '1000px'
      }
    }
  }
}
</script>
<style scoped>
.f28 {
  font-size: .28rem;
}
.vue-menu-list {
  list-style-type: none;
  padding: 0;
}
.vue-menu-list > li {
  display: inline-block;
  padding: 0 10px;
}
</style>
