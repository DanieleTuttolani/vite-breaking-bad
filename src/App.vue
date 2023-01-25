<script>
import axios from 'axios';
import OptionSelector from './components/OptionSelector.vue';
import { store } from './assets/data/store';
import CardSection from './components/CardSection.vue';
export default {
    data() {
        return {
            store
        }
    },
    methods: {
        fetchAllApi(url) {
            axios.get(url)
                .then(res => {
                    this.store.pokemons = res.data.docs
                })
        }
    },
    components: {
        CardSection,
        OptionSelector
    },
    created() {
        axios.get(store.pokeUri)
            .then(res => {
                this.store.pokemons = res.data.docs
            })

        axios.get(store.pokeTypesUri)
            .then(res => {
                this.store.pokeTypes = res.data
            })
    }
}
</script>

<template>
    <div class="container">
        <div class="main-title mt-5">
            <h1 class=" text-center text-light">Il Mio Pokedex</h1>
        </div>
        <OptionSelector />
        <!-- card section -->
        <CardSection />
    </div>
</template>

<style lang="scss">
@use './assets/scss/style.scss' as *;

h1 {
    text-shadow: black 0 0 3px;
}
</style>
