<template>
    <main class="main">
        <div class="container">
            <ul class="card">
                <Card v-for="card in store.cards" :key="card.id" :card="card"/>
                <!-- <li v-for="card in store.cards" :key="card.id">
                    <img :src="card.card_images[0].image_url" alt="immagine">
                    <p>{{ card.name }}</p>
                    <p>{{ card.type }}</p>
                </li> -->
            </ul>
        </div>

    </main>
</template>
  
<script>
import axios from 'axios'
import store from './store'
import Card from './Card.vue'

export default {
    components: {
        Card
    },
    data() {
        return {
            store,
        }
    },
    methods: {
        fetchCard() {
            axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0')
                .then((res) => {
                    console.log(res)
                    this.store.cards = res.data.data
                    console.log(store, 'store')
                })

        }
    },
    mounted() {
        this.fetchCard()
    },
}

</script>
  
<style lang="scss" scoped>
.main {
    background-color: darksalmon;
}

.card {
    display: grid;
    gap: 20px;
    grid-template-columns: repeat(5, 1fr);
}
</style>