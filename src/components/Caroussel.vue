<template>
    <div>
        <slot></slot>
    </div>
</template>


<script>
export default {
    data(){
        console.log(slides)
        return {
            index :0 ,
            slides: this.$children
        }
    }
}
</script>
