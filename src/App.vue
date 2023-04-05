<template>
  <div id="contain">
    <img id="image" alt="Vue logo" src="./assets/instagram.png">
  </div>
  <PostForm msg="Welcome to Instagram-Auto-Posting page!"/>
</template>

<script>
import PostForm from './components/Form.vue'

export default {
  name: 'App',
  components: {
    PostForm
  },
  mounted() {
    document.title = "Instagram-Auto-Post"
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #FFFFFF;
  margin-top: 30px;
  
}
#contain {
    display: flex;
    justify-content: center;
  }
#image {
  width: 100px;
  height: 100px;
}
</style>
