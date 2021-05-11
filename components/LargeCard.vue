<template>
    <NuxtLink class="card" :to="`/products/${card.id}`">
        <!-- in src carica l'immagine collegata alla singola card oppure, in caso non fosse presente,
        utilizza l'immagine fe1.jpg. -->
        <img :src="require(`@/assets/images/${card.image || 'fe1.jpg'}`)" alt="..." class="image">
        <h3 class="header">{{card.title}}</h3>
        <p class="snippet">{{card.snippet}}</p>
    </NuxtLink>
</template>

<script>
export default {
    props: {
        card: Object
    }

}
</script>

<style scoped>
    .card {
        width: 31.5%;
        height: 25rem;
        border: none;
        overflow: hidden;
        padding: 0;
        cursor: pointer;
        text-decoration: none;
    }
    .image {
        height: 65%;
        border-radius: 0.5rem;
    }
    .header {
        font-size: 1.15rem;
        margin-top: 0.4rem;
        color: black;
    }
    .snippet {
        color: grey
    }
</style>