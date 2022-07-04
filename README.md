# hello-vue

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Lints and fixes files
```
npm run lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).

### To install router
vue add router

### To install axios
npm i axios 


sample 1: in App.vue -------------- 1

<template>
  <div id="app">
    <input type="text" v-model="name" />
    <h1>Hello {{ name }} </h1>
  </div>
</template>

<script>
  export default({
    el: "#app",
    data(){
      return {
        name: 'moe'
      }
    }
  })
</script>


sample 2 (search bar): App.vue ------------- 2

<template>
  <input type="text" v-model="input" placeholder="Search fruits..." />
  <div class="item fruit" v-for="fruit in filteredList()" :key="fruit">
    <p>{{ fruit }}</p>
  </div>
  <div class="item error" v-if="input&&!filteredList().length">
     <p>No results found!</p>
  </div>
</template>

<script setup>
import { ref } from "vue";
let input = ref("");
const fruits = ["apple", "banana", "orange"];
function filteredList() {
  return fruits.filter((fruit) =>
    fruit.toLowerCase().includes(input.value.toLowerCase())
  );
}
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Montserrat&display=swap");

* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
  font-family: "Montserrat", sans-serif;
}

body {
  padding: 20px;
  min-height: 100vh;
  background-color: rgb(234, 242, 255);
}

input {
  display: block;
  width: 350px;
  margin: 20px auto;
  padding: 10px 45px;
  background: white url("https://img.icons8.com/arcade/100/000000/experimental-search-arcade.png") no-repeat 15px center;
  background-size: 15px 15px;
  font-size: 16px;
  border: none;
  border-radius: 5px;
  box-shadow: rgba(50, 50, 93, 0.25) 0px 2px 5px -1px,
    rgba(0, 0, 0, 0.3) 0px 1px 3px -1px;
}

.item {
  width: 350px;
  margin: 0 auto 10px auto;
  padding: 10px 20px;
  color: white;
  border-radius: 5px;
  box-shadow: rgba(0, 0, 0, 0.1) 0px 1px 3px 0px,
    rgba(0, 0, 0, 0.06) 0px 1px 2px 0px;
}

.fruit {
  background-color: rgb(97, 62, 252);
  cursor: pointer;
}

.error {
  background-color: tomato;
}
</style>

sample 3 (search bar) ----------   3
<template>
  <div id="app">
    <input v-model="searchQuery">
    <div v-for="r of resultQuery" :key="r.id">{{r.title}}</div>
  </div>
</template>
<script>
export default {
  name: "App",
  data() {
    return {
      searchQuery: undefined,
      resources: [
        { id: 1, title: "javascript for dummies" },
        { id: 2, title: "vue for dummies" },
        { id: 3, title: "dos for dummies" },
        { id: 4, title: "windows for dummies" },
        { id: 5, title: "html for dummies" }
      ]
    };
  },
  computed: {
    resultQuery() {
      if (this.searchQuery) {
        return this.resources.filter(item => {
          return this.searchQuery
            .toLowerCase()
            .split(" ")
            .every(v => item.title.toLowerCase().includes(v));
        });
      } else {
        return this.resources;
      }
    }
  }
};
</script>





sample 4 (using axios) ------------  4

<template>
<div class="mainDiv">
    <div v-for="post in posts" :key="post" class="post">
        {{post.title}}
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
</style> 