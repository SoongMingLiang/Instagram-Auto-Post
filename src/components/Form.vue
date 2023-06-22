<template>
  <div class="form">
    <h1>{{ msg }}</h1>
    <p id="link">
      <a href="https://www.instagram.com/test.auto_post/" target="_blank" rel="noopener">Instagram Page</a>
    </p>
    <form id="post">
      <p id="label"><label>Enter your text:</label></p>
      <textarea v-model="content" name="content" id="textbox" rows="12"></textarea>
      <div id="container">
        <input type="button" value="POST" id="submit" @click="handleClick">
      </div>
    </form>
  </div>
</template>

<script>
export default {
  name: 'PostForm',
  props: {
    msg: String
  },
  methods: {
    handleClick(){
      let post = this.content
      console.log(post)
      let data = {
        content: post
      }
      console.log(data)
      if(post.length !== 0){
        fetch('https://instagram-posts-api.onrender.com/post/new', {
          method: 'POST',
          headers: {
            'Content-Type': 'application/json; charset=UTF-8'
          },
          body: JSON.stringify(data)
        })
          .then(response => console.log(response))
          .then(alert('Posted to Instagram!'))
          .catch(err => console.log(err))
      }
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1,#link {
  text-align: center;
}
a {
  color: #FFFFFF;
  font-size: 20px;
}
a:hover {
  color: #428db9;
  transition: 1s;
}
label {
  display: block;
  margin-bottom: 10px;
  margin-left: 25%;
}
#textbox {
  font-size: 16px;
  border-radius: 10px;
  padding: 10px;
  width: 50%;
  resize: none;
  margin-left: 25%;
}
#container {
    display: flex;
    justify-content: center;
}
#submit {
  margin-top: 10px;
  font-size: 16px;
  border-radius: 10px;
  padding: 10px 50px 10px 50px;
}
#submit:hover {
  background-color: #428db9;
  color:#FFFFFF;
  transition: 1s;
}
</style>
