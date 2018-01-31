<template>
  <div id="app">
    <vue-menu-view/>
  </div>
</template>

<script>
import VueMenuView from './components/vue-menu-view'

export default {
  name: 'App',
  components: {
    VueMenuView
  }
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
}
</style>
