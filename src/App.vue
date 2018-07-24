<template>
    <caroussel>
      
      <caroussel-slide>
        <div class="caroussel-text" style="position:absolute;left:0;right:0;text-align:center;top:70%;color:#FFF;font-size:2em;">Ok 0</div>
        <img src="http://via.placeholder.com/630x300" alt="" width="100%">
      </caroussel-slide>
      
      <caroussel-slide>
        <div class="caroussel-text" style="position:absolute;left:0;right:0;text-align:center;top:70%;color:#FFF;font-size:2em;">Ok 111</div>
        <img src="http://via.placeholder.com/630x300" alt="" width="100%">
      </caroussel-slide>
      
      <caroussel-slide>
        <div class="caroussel-text" style="position:absolute;left:0;right:0;text-align:center;top:70%;color:#FFF;font-size:2em;">Ok 22222</div>
        <img src="http://via.placeholder.com/630x300" alt="" width="100%">
      </caroussel-slide>
      
      <caroussel-slide>
        <div class="caroussel-text" style="position:absolute;left:0;right:0;text-align:center;top:70%;color:#FFF;font-size:2em;">Ok 33333333</div>
        <img src="http://via.placeholder.com/630x300" alt="" width="100%">
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
