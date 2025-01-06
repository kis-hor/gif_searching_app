<template>
    <div class="gif" :style="`background-image: url(${gif.images.original.url}) ;`"></div>
    <input rel="url" readonly type="text" :value="gif.images.original.url" style="flex: 1;"/>
    <button @click="copyUrl">Copy</button>
</template>

<script>


export default {
  name: "GifsView",
  props:{
    gif:Object
  },
  methods:{
    copyUrl(){
      this.$refs.url.select();
      document.execCommand('copy');
      this.$refs.url.value = 'Copied!';
    }
  }
}
</script>

<style scoped>
.gif{
    width: 240px;
    height: 240px;
    background-repeat: no-repeat;
    background-size: cover;
    margin-bottom: 20px;
    background-position: center;
    display: flex;
    justify-content: space-between;
    align-items: flex-end; 
}
</style>
