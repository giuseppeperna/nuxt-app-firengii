<template>
<div>
  <div class="container">
      <LargeCardDisplay v-for="cardInfo in largeCardInfo.slice(0,1)" :key="cardInfo.id + '_products'" 
      :cardSection ="cardInfo" />
      <SmallCardDisplay v-for="cardInfo in smallCardInfo" :key="cardInfo.id + 'sm-products'"
      :smallCardSection="cardInfo" />
  </div>
</div>
  
</template>

<script>
import {largeCardSections, smallCardSections} from '@/assets/data.js'
export default {
  head() {
    return {
      title: "Products"
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

<style scoped>

</style>