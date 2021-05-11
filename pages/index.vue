<template>
<div>
  <div class="container">
    
    <!-- Nuxt importa automaticamente i components creati, senza bisogno di doverli registrare. -->
    <Hero />
    <LargeCardDisplay v-for="cardInfo in largeCardInfo" :key="cardInfo.id + '_large'" :cardSection="cardInfo" />
    <SmallCardDisplay v-for="cardSmall in smallCardInfo" :key="cardSmall.id +'_small'" :smallCardSection="cardSmall" />
  </div>
</div>
  
</template>

<script>
import {largeCardSections, smallCardSections} from '@/assets/data.js';

export default {
  head() {
    return {
      title: "Firengii",
    }
  },
  data() {
    return {
      largeCardInfo: largeCardSections,
      smallCardInfo: smallCardSections
    }
  }
}
</script>

<style>

</style>
