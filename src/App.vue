<template>
    <caroussel>
      
      <caroussel-slide v-for="i in slides" v-bind:key="i" :index="i-1" >
        <div class="caroussel-text" 
        style="position:absolute;left:0;right:0;text-align:center;top:70%;color:#FFF;font-size:2em;">
          Ok {{ i }}
        </div>
        <img :src="'http://via.placeholder.com/580x200/'+ i " alt="" width="100%">
      </caroussel-slide>
      <div>
        <button class="ui button green" @click.prevent="addSlide">Add Slide</button>
        <button class="ui button red" @click.prevent="removeSlide">Delete Slide</button>
      </div>
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
        slides: 3,
        msg: 'Welcome to Your Vue.js App'
      }
    },
    methods:{
      addSlide(){
        this.slides++
      },
      removeSlide(){
        this.slides--
      }
    }
  }
</script>
