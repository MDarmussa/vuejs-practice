<template>
<div class="mainDiv">
    <div v-for="post in posts" :key="post" class="post">
        <h1>{{post.id}}</h1>
        <p>{{post.title}}</p>
    </div>
</div>
</template>

<script>
import axios from 'axios';


export default {
    name: 'consume-rest-api',
    data(){
        return{
            posts: null
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
            });
    }
}
</script>

<style scoped>
  .mainDiv {
    color: red;
    border-style: solid blue;
  }

  p {
    color: green;
  }
</style> 