<template>
  <div id="app">
    <br><br><br><br>
  <h1 class="h1element">I am a search bar 2</h1>
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

<style>
.h1element {
    color: red;
}
</style>