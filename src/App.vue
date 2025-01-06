<template>
  <Search @fetch-gifs="onFetch" />
  <gif-lists :gifs="gifs" />
</template>

<script>
import GifLists from './components/GifLists.vue';
import Search from './components/Search.vue';


export default {
  name: 'App',
  components: {
    GifLists,
    Search
  },
  data() {
    return {
      gifs: []
    }
  },
  methods: {
    onFetch(result){
      this.gifs = result;
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
    * {
        box-sizing: border-box;
    }
    body{
        font-family: Arial, sans-serif;
        padding: 50px;
    }
</style>
