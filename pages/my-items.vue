<template>
  <div class="container">
      <MyItem v-for="rental in myRentals" :key="rental.id" :item="rental"/>
  </div>
</template>

<script>
// Importa i dati provenienti dallo state manager di Vuex
import {mapState} from 'vuex';

export default {
  head() {
    return {
      title: "My Items"
    }
  },
  // Scelta del layout da seguire per il component.
  layout: 'no-nav',
  computed: {
    // Mappa i dati provenienti dall'array myRentals nello state manager Vuex
    ...mapState(['myRentals'])
  }
}
</script>

<style scoped>

</style>