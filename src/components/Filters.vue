<template>
    <div class="container">
        <input class="input-search" @keyup.enter="$emit('searchForName')" type="text" placeholder="Filtra per nome" v-model="store.searchCard">
        <select class="input-search" name="" id="">
            <option value="">--Filtra per--</option>
            <option value=""></option>
            <option value=""></option>
        </select>
    </div>
</template>
  
<script>
import store from './store'

export default {
    data() {
        return {
            store,
        }
    },
}
</script>
  
<style lang="scss" scoped>
.input-search {
    padding: 10px 25px;
    border-radius: 5px;
    margin-left: 30px;
}
</style>