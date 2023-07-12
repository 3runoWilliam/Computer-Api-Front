<script>
import { ref } from 'vue'
export default {
    name: "formulario",
    data () {
        return {
            nome: '',
            descricao: '',
            preco: '',
            computadores: [{}],
        }
    },
    methods:{
        onClick(){
            const computador = {
                "cNome": '',
                "cDescricao": '',
                "cPreco": '',
            }
            computador.cNome = this.nome
            computador.cDescricao = this.descricao
            computador.cPreco = this.preco

            console.log(computador)
            this.computadores.push(computador)
            console.log(this.computadores)
            return computador
        }
    }
}
</script>

<template>
    <main class="pgCad">
        <h1>Cadastrar Computador</h1>
        <form class="formulario">
            <input v-model="nome" class="input" id="nome" placeholder="Nome do computador" type="text">

            <input v-model="descricao" class="input" id="descricao" placeholder="Descricao do computador" type="text">

            <input v-model="preco" class="input" id="preco" placeholder="Preco do computador" type="text">

            <button type="button" @click="onClick()" class="button">Enviar</button>
        </form>
    </main>
</template>

<style scoped>

button {
  font-weight: bold;
}
.formulario{
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    gap: 15px;
}
.input{
    width: 300px;
    height: 40px;
    box-shadow: 0 0 17px #f00;
    border-radius: 15px;
    background-color: rgba(1, 1, 1, 0);
    border: 2px solid #f00;
    color: #fff;
}
.input::placeholder{
    color: #fff;
    text-align: center;
}
.button{
    width: 130px;
    height: 40px;
    box-shadow: 0 0 17px #f00;
    border-radius: 15px;
    background-color: rgba(1, 1, 1, 0);
    border: 2px solid #f00;
    color: #fff;
}
.button:hover{
    color: #000;
    background-color: #fff;
    transition: 500ms;
}
.pgCad{
    display: flex;
    flex: 1;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    gap: 4rem;
}
.pgCad h1{
    font-size: 2.5rem;
    color: #fff;
    font-family: Arial, Helvetica, sans-serif;
}


</style>
