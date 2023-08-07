<script setup lang="ts">
import MarqueeBox from '../components/MarqueeBox.vue';
// @ts-ignore
import Marquee from '../components/Marquee.vue';
import marqueeRight from '../components/MarqueeRight.vue'
import marqueePic from '../components/MarqueePic.vue'
defineProps<{
  msg: string
}>()
</script>

<template>
  <div class="">

     
    <marqueeRight> </marqueeRight>
   <div>
  
<marqueePic></marqueePic>
   </div>
   <marqueeRight> </marqueeRight>
   <div>
    MAGO 图片轮播

   </div>
   <marqueeBox></marqueeBox>
  </div>
</template>

<style scoped>

</style>
