<template>
    <caroussel>
      <caroussel-slide></caroussel-slide>
      <caroussel-slide></caroussel-slide>
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
