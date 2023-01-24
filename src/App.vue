<script>
import axios from 'axios';
import { store } from './assets/data/store';
import CardSection from './components/CardSection.vue';
export default {
    data (){
        return{
            store
        }
    },
    components :{
        CardSection
    },
    created() {
        axios.get(this.store.pokeUri)
        .then(res =>{
            this.store.pokemons = res.data.docs
        })
    }
}
</script>

<template>
  <div class="container">
        <div class="main-title mt-5">
            <h1 class=" text-center text-light">Il Mio Pokedex</h1>
        </div>
        <!-- card section -->
        <CardSection/>
  </div>
</template>

<style lang="scss">
@use './assets/scss/style.scss'as *;
h1{
    text-shadow: black 0 0 3px;
}
</style>
