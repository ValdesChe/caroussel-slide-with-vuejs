<template>
    <caroussel>
        <caroussel-slide>Carroussel 1</caroussel-slide>
        
        <caroussel-slide>Carroussel 2</caroussel-slide>
    
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
