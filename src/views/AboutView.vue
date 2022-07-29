<template>
  <div class="about">
    <h1>This is an about page</h1>
    <TestComp />
    <SearchBarVue />
    <SearchBar2 />
    <!-- <LocalDataVue /> -->
    <AxiosComp2Vue />
    <!-- <AxiosComp /> -->
  </div>
</template>

<script>
import TestComp from '@/components/TestComp.vue'
import SearchBarVue from '@/components/SearchBar.vue'
import SearchBar2 from '@/components/SearchBar2.vue'
// import AxiosComp from '@/components/AxiosComp.vue'
// import AxiosComp2Vue from '@/components/AxiosComp2.vue'
// import LocalDataVue from '@/components/LocalData.vue'

export default {
  name: 'AboutView',
  components: {
    TestComp,
    SearchBarVue,
    SearchBar2,
    // AxiosComp2Vue,
    // AxiosComp,
    // LocalDataVue
  }
}
</script>
