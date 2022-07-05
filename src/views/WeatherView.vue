<template>
    <div>  
        hello
        <Weather />  
    </div>
</template>

<script>
import Weather from '@/components/Weather.vue'

    export default {
        name: "WeatherView",
        components: {
            Weather
        }
        
    }
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;


</style>