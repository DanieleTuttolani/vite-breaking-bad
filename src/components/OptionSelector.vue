<script>
import { store } from '../assets/data/store';
export default {
    data() {
        return {
            store
        }
    }
}
</script>
<template>
    <select class="form-select my-5" aria-label="Default select example">
        <option selected>Choose a Pokemon type</option>
        <option v-for="pokeType in store.pokeTypes">{{ pokeType }}</option>
    </select>
</template>
<style>
.form-select {
    width: 50%;
}
</style>