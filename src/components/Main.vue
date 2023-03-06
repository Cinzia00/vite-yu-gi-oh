<template>
    <main class="main">
        <Filters @searchForName="fetchCard" />
        <div class="container">
            <ul class="card">
                <Card class="single-card" v-for="card in store.cards" :key="card.id" :card="card" />
            </ul>
        </div>
    </main>
</template>
  
<script>
import axios from 'axios'
import store from './store'
import Card from './Card.vue'
import Filters from './Filters.vue'

export default {
    components: {
        Card,
        Filters,
    },
    data() {
        return {
            store,
        }
    },
    methods: {
        fetchCard() {
            const searchCard = this.store.searchCard
            axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0', {
                params: {
                    fname: searchCard,
                }

            }).then((res) => {
                console.log(res)
                this.store.cards = res.data.data
                console.log(store, 'store')
            }).catch((error) => {
                this.store.cards = [];
            })

        }
    },
    mounted() {
        this.fetchCard()
    },
}

</script>
  
<style lang="scss" scoped>
@use '../general.scss' as *;

.container {
    padding: 50px;
    margin: 0 auto;
    background-color: darksalmon;
}

.card {
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
    gap: 20px;

    .single-card {
        flex-basis: calc(100% / 5 - 80px);
    }
}
</style>