<template>
  
  <div> 
    <ul :key="posts">
    <li v-for="post of posts">
      <div class="note-card mdl-card mdl-shadow--2dp">
        <div class="mdl-card__title">
          <h2 class="mdl-card__title-text">{{post.title}}</h2>
        </div>
        <div class="mdl-card__supporting-text">
          {{post.body}}
        </div>
        <div class="mdl-card__actions mdl-card--border">
          <a class="mdl-button mdl-button--colored mdl-js-button mdl-js-ripple-effect">
            Delete
          </a>
        </div>
        <div class="mdl-card__menu">
          <button class="mdl-button mdl-button--icon mdl-js-button mdl-js-ripple-effect">
            <i class="material-icons">share</i>
          </button>
        </div>
      </div>
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
      console.log(JSON.stringify(this.posts))
    })
    .catch(e => {
      this.errors.push(e)
    })
  },
  methods(){
    
  }
}
</script>

<style scoped>
  .note-card{
    margin-bottom: 1em
  }
</style>

