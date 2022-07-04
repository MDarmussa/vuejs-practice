<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <h1><HelloWorld msg='I am a message coming from hello world component' /></h1>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'HomeView',
  components: {
    HelloWorld
  }
}
</script>
