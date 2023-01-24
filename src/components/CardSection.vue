<script>
import { store } from '../assets/data/store';

export default{
    data (){
        return{
            store
        }
    }
}
</script>


<template>
    <div class="row row-cols-4 cs-card-wrapper p-3">
            <div v-for="pokemon in store.pokemons" :key="pokemon.id" class="card-wrapper my-3">
                <div class="card text-light" :class="pokemon.color" style="width: 18rem;">
                    <img :src="pokemon.imageUrl" class="card-img-top"  alt="...">
                    <div class="card-body">
                        <h5 class="card-title">{{ pokemon.name }}</h5>
                        <p class="card-text"> Pokemon HP :{{ pokemon.hp }}</p>
                        <p class="card-text"> Pokemon ATK :{{ pokemon.atk }}</p>
                        
                    </div>
                </div>
            </div>
            
    </div>
</template>



<style lang="scss" scoped>
.cs-card-wrapper{
    min-height: 500px;
    background-color: rgb(223, 223, 223);
    border-radius: 30px;
    .card-img-top{
        height: 280px;
        width: 286px;
    }
    .Green{
        background-color: green;
    }
    .Red{
        background-color: darkred;
    }
    .Blue{
        background-color: dodgerblue;
    }
    .Brown , .Purple{
        background-color: gray;
    }
    .Pink{
        background-color: pink;
    }
}
</style>