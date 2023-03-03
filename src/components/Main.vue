<template>
    <main class="main">
        <div class="container">
            <ul class="card">
                <li>
                    <img src="" alt="immagine">
                    <p>nome</p>
                    <p>tipo</p>
                </li>
            </ul>
        </div>

    </main>
</template>
  
<script>
import axios from 'axios'
import store from './store'


export default {
    data() {
        return {
            store,
        }
    },
    methods: {
        fetchCard() {
            axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php')
                .then((res) => {
                    console.log(res.data)
                })

        }
    }
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