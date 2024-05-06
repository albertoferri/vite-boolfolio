<script>


import AppFooter from './components/AppFooter.vue';
import AppHeader from './components/AppHeader.vue';


export default {

  data() {
    return {
      
    } 
  },
  
  components: {
    AppFooter,
    AppHeader
  },

  mounted() {

  },

  methods: {

  },
}

</script>

<template>

 <AppHeader></AppHeader>

  <div class="py-5">

    <router-view></router-view>

  </div>

  <AppFooter></AppFooter>

</template>

<style lang="scss" scoped>

</style>