<script setup lang="ts">
import WelcomeItem from './WelcomeItem.vue'
import DocumentationIcon from './icons/IconDocumentation.vue'
import ToolingIcon from './icons/IconTooling.vue'
import EcosystemIcon from './icons/IconEcosystem.vue'
import CommunityIcon from './icons/IconCommunity.vue'
import SupportIcon from './icons/IconSupport.vue'
 
defineProps<{
  name: String,
  title:String,
  minTitle:String,
  images:String
}>()
</script>

<template>
  <div class="showSpace">
    <div class="leftBox">
      {{ name }}
    </div>
    <div>
      <div class="titleBox">
           {{ title }}
          <div style="font-size:1rem;">
            {{ minTitle }}
          </div>
      </div>
      <div style="height: 700px;">
        <img class="show"  :src="images" alt="">
      </div>
      <div class="nameBox">
        
        {{ name }}
      </div>
    </div>
  </div>
  <div>
  
  </div>


</template>
<style>
.titleBox{
  background: rgba(201, 201, 201, 0.452);
  color: white;
  bottom: 300px;
  position: absolute;
  padding: 20px 20px 20px 80px;
  font-size: 3.5rem;
  font-weight: 500;
  letter-spacing: 0.3em;
  backdrop-filter: blur(5px);
}
.showSpace{
  position: relative;
  display: grid;
  grid-template-columns: 1fr 15fr;
}
.show{
 
  height: 700px;
}
.leftBox{
  padding: 5px;
  font-size: 4rem;
  font-weight: 500;
  letter-spacing: 0.3em;
  color: white;
  background: black;
  writing-mode:vertical-lr;
}
.nameBox{
  padding: 5px;
  font-size: 4rem;
  font-weight: 500;
  letter-spacing: 0.3em;
  color: white;
  background: black;
 
}
</style>