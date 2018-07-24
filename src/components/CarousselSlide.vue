<template>
    <transition  :name="transition">
      <div  v-show="visible">
        <slot></slot>
      </div>
    </transition>
</template>

<script>
export default {
  props:{
    index:{type:Number , default:0}
  },
  data() {
    return {
      index : 0
    }
  },
  computed:{
    transition(){
      if ( this.$parent.direction != null ) {
        return  'slide' + this.$parent.direction
      }
    },
    visible(){
      return this.index == this.$parent.index
    }
  }
};
</script>

<style>

  .slideRigth-enter-active{
    animation: slideRigthIn .7s;
  }

  .slideRigth-leave-active{
    animation: slideRigthOut .7s;
    position: absolute;
    top: 0;
    left: 0;
    bottom: 0;
    right: 0;
    width: 100%;
  }

  @keyframes slideRigthIn {
    from {
      transform: translateX(100%);
    }
    to{
      transform: translateX(0);
    }
    
  }

  @keyframes slideRigthOut {
    from {
      transform: translateX(0);
    }
    to{
      transform: translateX(-100%);
    }
    
  }

  .slideLeft-enter-active{
    animation: slideLeftIn .7s;
  }

  .slideLeft-leave-active{
    animation: slideLeftOut .7s;
    position: absolute;
    top: 0;
    left: 0;
    bottom: 0;
    right: 0;
    width: 100%;
  }

  @keyframes slideLeftIn {
    from {
      transform: translateX(-100%);
    }
    to{
      transform: translateX(0);
    }
    
  }

  @keyframes slideLeftOut {
    from {
      transform: translateX(0);
    }
    to{
      transform: translateX(100%);
    }
    
  }
</style>

