<template>
    <div id="gifList">
        <gif v-for="gif in gifs" :key="gif.id" :gif="gif" /> 
    </div>
  </template>
  
  <script>
  import Gif from './Gif.vue';
  export default {
    name: "GifLists",
    components: {
      Gif
    },
    props:{
    gifs:Array
    }
  }
  </script>
  
  <style scoped>
    #gifList{
        margin-top: 20px;
        display: flex;
        flex-wrap: wrap;
        justify-content: space-between;
    }
  </style>
  