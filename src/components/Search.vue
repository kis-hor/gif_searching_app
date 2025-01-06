<template>
  <input placeholder="Search for GIFs" v-model="keyword" @input="onInput" />
</template>

<script>


export default {
  name: "SearchGIF",
  data(){
    return {
      keyword: '',
      timeout: null
    }
  },
  methods: {
    onInput(){
      clearTimeout(this.timeout)
      this.timeout = setTimeout(() => {
        this.search()
      }, 500)
    },
    search(){
        fetch(`https://api.giphy.com/v1/gifs/search?api_key=acaDP7PhxVduIrq7rkwvSmNDQnarLh7d&q=${this.keyword}&limit=25&offset=0&rating=g&lang=en`)
      .then(response => response.json())
      .then(
        result => {console.log(result);
        this.$emit('fetch-gifs', result.data);
        })
    }
  }
}

// API Key: acaDP7PhxVduIrq7rkwvSmNDQnarLh7d
</script>

<style scoped>
    input
    {
        width: 100%;
        padding: 12px 20px;
        margin: 8px 0;
        border-radius: 10px;
        outline: 0;
        display: block;
    }
    input:focus{
        border-color: blue;
    }
</style>
