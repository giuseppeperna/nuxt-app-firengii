<template>
  <div class="container">
      <h4 class="header">{{smallCardSection.title}}</h4>
      <div class="card-container">
         <SmallCard v-for="card in smallCardSection.cards" :key="card.id" :card="card" />
      </div>
  </div>
</template>

<script>
export default {
    props: {
        smallCardSection: Object,
    }
}
</script>

<style scoped>
    .container {
        padding: 2rem 0
    }
    .header {
        font-weight: 700;
        font-size: 1.5rem;
        margin-bottom: 2rem;
    }
    .card-container {
        display: flex;
        justify-content: space-between;
        flex-wrap: wrap;
    }
</style>