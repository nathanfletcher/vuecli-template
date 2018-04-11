<template>
  
  <div> 
    <ul>
    <li v-for="post of posts">
      <p><strong>{{post.title}}</strong></p>
      <p>{{post.body}}</p>
    </li>
  </ul>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  name:'Notes',
  data() {
    return{
      notes:[],
      posts:[]
    }
  },
  created() {
    axios.get(`http://jsonplaceholder.typicode.com/posts`)
    .then(response => {
      // JSON responses are automatically parsed.
      this.posts = response.data
    })
    .catch(e => {
      this.errors.push(e)
    })
  }
}
</script>
