<template>
    <li>
        <img :src="card.card_images[0].image_url" alt="immagine">
        <p>{{ card.name }}</p>
        <p>{{ card.type }}</p>
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

</style>