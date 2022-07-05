<template>
  <div class="about">
    <h1>This is an about page</h1>
    <TestComp />
  </div>
</template>

<script>
import TestComp from '@/components/TestComp.vue'
export default {
  name: 'AboutView',
  components: {
    TestComp
  }
}
</script>
