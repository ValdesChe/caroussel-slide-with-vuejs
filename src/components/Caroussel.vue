<template>
    <div>
        <slot></slot>
        <div v-show="hasSlide">
            <button class="ui secondary button" @click="previousSlide">Previous</button>
            <button class="ui primary button" @click="nextSlide">Next</button>
        </div>
    </div>
</template>


<script>
export default {
    data(){
        
        return {
            //  fOR CURRENT SLIDE   
            index :0 ,
            slides: []
        }
    },
    methods:{
        nextSlide(){
            
            this.index++
            if(this.index >= this.slideCount)
                this.index = 0
         
        },
        previousSlide(){
            this.index--
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
