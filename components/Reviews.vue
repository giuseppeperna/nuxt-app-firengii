<template>
  <div>
      <h3>Customer Reviews</h3>
      <!-- $fetchState permette di accedere all'oggetto che gestisce il fetch dei dati. Se lo stato
      non è pending, allora mostra le reviews recuperate. -->
      <div v-if="!$fetchState.pending">
          <ReviewCard v-for="reviewer in reviewers.results" :key="reviewer.login.uuid" :review="reviewer"/>
      </div>
      <!-- Altrimenti mostra un messaggio o icona di caricamento. -->
      <div v-else>
          Loading...
      </div>
  </div>
</template>

<script>
export default {
    data() {
        return {
            reviewers: []
        }
    },
    // Recupera i dati sulle reviews dall'API.
    async fetch() {
        this.reviewers = await fetch('https://randomuser.me/api/?results=5')
        .then(res => res.json());
    }

}
</script>

<style scoped>

</style>