<template>
  <div class="">
    <Swipe/> 
  </div>
</template>


<script>

import Vue from 'vue'
import VueAwesomeSwiper from 'vue-awesome-swiper'
import Swipe from '@/components/Swipe'
Vue.use(VueAwesomeSwiper)

  export default {
    components: {
      Swipe,
    }
  }
</script>


