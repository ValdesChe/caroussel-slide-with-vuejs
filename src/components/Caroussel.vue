<template>
    <div class="caroussel">
        <slot></slot>
        <div v-show="hasSlide">
            <button class="caroussel__nav caroussel__prev " @click.prevent ="previousSlide"></button>
            <button class="caroussel__nav caroussel__next " @click.prevent="nextSlide"></button>
            <div class="caroussel__pagination">
               <button v-bind:key="n" v-for="n in slideCount" @click.prevent="goto(n-1)" :class="{active: n-1 == index}"></button>
            </div>
        </div>
        
    </div>
</template>


<script>
export default {
    
    data(){
        return {
            //  fOR CURRENT SLIDE   
            index:0,
            slides: [],
            direction :  "Rigth"
        }
    },
    methods:{
        goto(index){
            this.direction = (this.index > index) ? "Left" : "Rigth"
            this.index = index
       },
        nextSlide(){
            
            this.index++
            this.direction = "Rigth"
            if(this.index >= this.slideCount)
                this.index = 0
         
        },
        previousSlide(){
            this.index--
            this.direction = "Left"
            if(this.index < 0 )
                this.index = this.slideCount -1
        }
    },
    watch:{
        slides(slides){
            if (this.index >= this.slideCount) {
                this.index = this.slideCount-1
            }s
        }
    },
    computed:{
        slideCount(){
            return this.slides.length
        },
        hasSlide(){
            return this.slides.length
        }
    },
    mounted(){
        this.slides = this.$children
        /* 
        this.slides.forEach( (slide , i ) => {
            slide.index = i
        })
        console.log(this.$children) */
    }
}
</script>
<style>
    button{
        
        border: none;
        padding: 0px;
        cursor: pointer;
    }
    .caroussel{
        position: relative;
    }

    .caroussel__nav{
        position: absolute;
        top:50%;
        margin-top: -31px;
        left: 10px;
        background: url(prev.png);
        width:56px;
        height: 56px;
    }

    .caroussel__prev{
        
    }

    .caroussel__next{
        right: 10px;
        left: auto;
        background-image: url(next.png)
    }

    .caroussel__pagination{
        position: absolute;
        top: 85%;
        left: 0;
        right: 0;
        text-align:center
        
    }

    .caroussel__pagination button{
        height: 10px;
        width:10px;
        margin: 5px;
        /*background: url(button.png); */
        opacity: 0.5;
        background: #000;
        border-radius: 10px;
        
    }

    .caroussel__pagination button.active{
       /*  background: url(rec.png) */
       
        background: #3e2dde;
        opacity: 0.7;
    }
</style>

