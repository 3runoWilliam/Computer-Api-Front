<script>
export default {
    name: "lista",
    data() {
        return{
            pokemons: [{}]
        }
    },
    methods: {

    },
    mounted() {
        fetch('https://pokeapi.co/api/v2/pokemon?limit=151')
        .then(response => {
            if (!response.ok) {
                throw new Error('Erro ao fazer a requisição da API.');
            }
            return response.json();
        })
        .then(data => {
            this.pokemons = data.results
            console.log(this.pokemons);
        })
        .catch(error => {
            console.error(error);
        });
    }
}


</script>

<template>
    <div class="lista">
        <div class="computador" v-for="pokemon in pokemons" :key="pokemon.index"> {{pokemon.name}} </div>
    </div>
</template>


<style>
.lista{
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;

}
.computador{
    border: 1px solid #f00;
    margin: 10px;
    width: 100px;
    height: 30px;
}
</style>
