<template>
    <div id="BoxPage">
        <span id="ContentTitle">
            Pokemon Management
        </span>

        <h2>Search a Pokemon</h2>

        <input placeholder="Search" type="text" 
        :value="input"
        @input="e => input = e.target.value">
        
        <div id="Pokemons">
            <div 
            id="Pokemon"
            v-for="pokemon in search"
            v-bind:key="pokemon.id">
                <div id="pokeProfile">
                    <h1>{{pokemon.name}}</h1>
                    <img v-bind:src="pokemon.img" alt="">
                </div>
                
                <div id="types">
                    <h3>Types</h3>
                    <ul>
                        <li 
                        v-for="ability in pokemon.types"
                        v-bind:key="ability.index">
                            {{ability.name}}
                        </li>
                    </ul>
                </div>

            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: "BoxPage",
        props: ["pokemons"],
        data: function () {
            return {
                input: ""
            }
        },
        computed: {
            search: function () {
                return this.pokemons.filter(
                    pokemon => pokemon.name.toLowerCase().includes(this.input.toLowerCase())
                )
            }
        }
    }
</script>

<style scoped>
    #BoxPage{
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
    }

    #Pokemons{
        display: flex;
        flex-direction: column;
        align-content: center;
        gap: 10px;
        margin-top: 10px;
    }

    #Pokemon{
        display: flex;
        justify-content: space-around;
        align-content: center;

        border: 1px black solid;
        padding: 20px;
        border-radius: 10px;
    }

    ul {
        padding: 0;
        list-style: none;
    }
    
    #types{
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: flex-start;
        padding: 10px;
    }

    input{
        padding: 10px;
        border: 1px black solid;
        border-radius: 10px;
        width: 80%;

    }

    input:focus { 
        outline: none !important;
        border-color: #007bff;
    }
</style>