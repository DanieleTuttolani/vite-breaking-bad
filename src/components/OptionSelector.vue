<script>
import { store } from '../assets/data/store';
export default {
    data() {
        return {
            store,
            choosenOption: ''
        }
    }
    ,
    emits: ['option-changing', 'option-value']
}
</script>
<template>

    <select v-model="choosenOption" @change="$emit('option-changing', choosenOption)" class="form-select my-5"
        aria-label="Default select example">
        <option selected>---</option>
        <option v-for="pokeType in store.pokeTypes">{{ pokeType }}</option>
    </select>

</template>
<style>
.form-select {
    width: 50%;
}
</style>