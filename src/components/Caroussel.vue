<template>
    <div class="caroussel">
        <slot></slot>
        <div v-show="hasSlide">
            <button class="caroussel__nav caroussel__prev " @click.prevent ="previousSlide"></button>
            <button class="caroussel__nav caroussel__next " @click.prevent="nextSlide"></button>
            <div class="caroussel__paginaation">
                 <button v-bind:key="n" v-for="n in slideCount" @click.prevent="goto(n-1)" :class="{active: n-1 == index}"> {{ n-1 }} </button>
            </div>
        </div>
    </div>
</template>


<script>
export default {
    data(){
        
        return {
            //  fOR CURRENT SLIDE   
            index :0 ,
            slides: [],
            direction : null
        }
    },
    methods:{
        goto(indexing){

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
    mounted(){
        this.slides = this.$children
        this.slides.forEach( (slide , i ) => {
            slide.index = i
        })
        console.log(this.$children)
    },
    computed:{
        slideCount(){
            return this.slides.length
        },
        hasSlide(){
            return this.slides.length
        }
    }
}
</script>
<style>
    .caroussel{

        position: relative;
    }

    .caroussel__nav{
        position: absolute;
        top:50%;
        margin-top: -31px;
        left: 10px;
        background: url(prev.png);
        width:60px;
        height: 60px;
    }

    .caroussel__prev{
        
    }

    .caroussel__next{
        right: 10px;
        left: auto;
        background-image: url(next.png)
    }
</style>

