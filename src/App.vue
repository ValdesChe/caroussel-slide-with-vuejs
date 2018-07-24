<template>
    <caroussel>
      <caroussel-slide>
        <img src="http://lorempixel.com/630/300" alt="">
      </caroussel-slide>
      <caroussel-slide>
        <img src="http://lorempicsum.com/futurama/630/300" alt="">
      </caroussel-slide>
      <caroussel-slide>
        <img src="http://lorempixel.com/630/300" alt="">
      </caroussel-slide>
     
      <caroussel-slide>
        <img src="http://lorempicsum.com/futurama/630/300" alt="">
      </caroussel-slide>
    </caroussel>
</template>

<script>
  import Caroussel from "./components/Caroussel" 
  import CarousselSlide from "./components/CarousselSlide" 
  export default {
    name: 'app',
    components:{
        Caroussel,
        CarousselSlide
    },
    data () {
      return {
        msg: 'Welcome to Your Vue.js App'
      }
    }
  }
</script>
