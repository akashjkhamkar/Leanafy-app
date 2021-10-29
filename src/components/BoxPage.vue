<template>
    <div id="BoxPage">
        <span id="ContentTitle">
            Pokemon Managment
        </span>

        <div class="Pokemons">
            <div 
            class="Pokemon"
            v-for="pokemon in pokemons"
            v-bind:key="pokemon.id">
                <h1>{{pokemon.name}}</h1>
                <img v-bind:src="pokemon.img" alt="">
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
</template>

<script>
    export default {
        name: "BoxPage",
        props: ["pokemons"]
    }
</script>

<style scoped>
    #BoxPage{
        display: flex;
        flex-direction: column;
        justify-content: center;
    }
</style>