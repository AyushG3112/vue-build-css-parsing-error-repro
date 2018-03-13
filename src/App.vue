<template>
  <div id="app">
    <button @click=loaderShow>Show Loader</button>
     <loading
     :show="showLoader"
     :label="loaderLabel">
 </loading>
  </div>
</template>

<script>
import Vue from 'vue';
import Loading from 'vue-full-loading';

Vue.use(Loading);

export default {
  name: 'app',
  components: {
    Loading
  },
  data() {
    return {
      showLoader: false,
      loaderLabel: "Loading"
    }
  },
  methods: {
    loaderShow() {
      this.showLoader = true;
      setTimeout(() => this.showLoader = false, 10000)
    }
  }
}
</script>

<style lang="less">
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
