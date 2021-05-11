<template>
  <div>
    <b-button id="show-btn" @click="showModal">Rent</b-button>

    <b-modal ref="my-modal" hide-footer title="Using Component Methods">
        <div class="calendar-container">
            <div class="text-container">
                <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Ea magni perferendis placeat beatae nostrum minus? Pariatur ab dolorum delectus fugiat, asperiores laborum, possimus dolor a autem tempora, commodi quaerat ipsam!</p>
            </div>
            <vc-date-picker 
            :value="null"
            color="indigo"
            is-dark
            is-range
            />
        </div>
        <b-button id="show-btn" variant="outline-danger" @click="onAddItem(product.id)">Order</b-button>

    </b-modal>
  </div>
</template>

<script>
import {mapMutations} from 'vuex';
export default {
    props: {
        product: Object
    },
    methods: {
      showModal() {
        this.$refs['my-modal'].show()
      },
      hideModal() {
        this.$refs['my-modal'].hide()
      },
      ...mapMutations(['addItem']),
      
      // Aggiunge l'oggetto alla lista dei rentals.
      onAddItem(id) {
        // Richiama il metodo addItem dell'array mutations di Vuex.
        this.addItem(id);
        // Chiude il modale del rental.
        this.hideModal()
        // Redirect alla pagina my-items dopo 1 secondo.
        setTimeout(() => {
            this.$router.push('/my-items');
        },1000);
      }

    },
  }
</script>

<style scoped>
    button {
        width: 100%;
        border: none;
        padding: 0.5rem;
        color: white;
        font-weight: 700;
        padding: 1rem 4rem;
        border-radius: 100rem;
        background-color: rgb(231, 81, 43);
        color: white;
        font-weight: 700;
        transition: 0.5s;
    }
    .calendar-container {
      margin: 0 auto;
      display: flex;
      justify-content: space-between;
    }
    p {
      color: grey
    }
    .text-container {
      padding: 0.5rem
    }
</style>