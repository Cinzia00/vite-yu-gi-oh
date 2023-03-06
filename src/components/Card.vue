<template>
    <li class="bg-color">
        <img :src="card.card_images[0].image_url" alt="immagine">
        <div class="desription">
            <p class="name">{{ card.name }}</p>
            <p>{{ card.type }}</p>
        </div>
    </li>
</template>
  
<script>


export default {
    props: {
        card: {
            type: Object,
            required: true
        }
    }
}

</script>
  
<style lang="scss" scoped>
.bg-color {
    background-color: darkgray;
    border-radius: 10px;
}

.desription {
    padding: 15px;
    text-align: center;
    font-size: 22px;

    .name {
        font-weight: bold;
    }
}

</style>