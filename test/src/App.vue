<template>
  <div id="app">
    <Header />
    <div id="content" class="content">
      <router-view></router-view>
    </div>
  </div>
</template>

<script>
import Header from './components/layout/Header.vue'

export default {
  name: 'App',
  components: {
    Header
  },
  
}
</script>

<style>
.ml-auto, .mx-auto {
    margin-left: auto!important;
}
</style>
