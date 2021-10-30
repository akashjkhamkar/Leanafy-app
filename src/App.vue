<template>
  <div id="megacontainer">
    <div id="subcontainer">
      <TopBar v-bind:current="getActivePage"/>
      <Hello/>

      <div id="pageContainer">
        <Inbound v-if="activePage === 1"/>
        <Box v-if="activePage === 2" v-bind:pokemons="pokemons"/>
        <Unbound v-if="activePage === 3"/>
      </div>

      <Footer v-on:isInbound="changePage($event)"/>
    </div>
  </div>
</template>

<script>
  import axios from 'axios';

  import TopBar from "./components/TopBar.vue"
  import Hello from "./components/Hello.vue"
  import Inbound from "./components/InboundPage.vue"
  import Unbound from "./components/UnboundPage.vue"
  import Box from "./components/BoxPage.vue"
  import Footer from "./components/Footer.vue"

  export default {
    name: 'App',
    components: {
      TopBar,
      Hello,
      Footer,
      Inbound,
      Unbound,
      Box
    },
    data: function() {
      return {
        activePage: 1,
        pokemons: []
      }
    },
    methods: {
      changePage: function(id){
        this.activePage = id;
      }
    },
    mounted () {
      axios.get("https://pokeapi.co/api/v2/pokemon?limit=80")
      .then(res => {
        
        // get pokemon list
        const pokelinks = res.data.results;
        return pokelinks;
      })
      .then(pokelinks => {
        pokelinks.map(item => {
          
          // now fetch indivisual pokemon
          axios.get(item.url)
          .then(res => {
              const data = res.data;
              const pokemon = {
                name: data.name,
                img: data.sprites.front_default,
                types: data.types.map((obj, index) => {
                    return {
                      id : index,
                      name : obj.type.name
                    }
                }),
                id: data.id
              }

              // add to the state
              this.pokemons.push(pokemon)
          })
        })
      })
      .catch(e => {
        alert("something went wrong", e)
      })
    },
    computed: {
        getActivePage() {
          if(this.activePage === 1){
              return "Inbound"
          }else if(this.activePage === 2){
            return "Packages"
          }else if(this.activePage === 3){
            return "Outbound"
          }else{
            return "null"
          }
      }
    }
  }

</script>

<style scoped>
  #megacontainer {
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 10px;
  }

  #subcontainer{
    width: 100%;
    min-height: 100vh;
    max-width: 400px;
    display: flex;
    flex-direction: column;
    gap: 20px;
    margin-bottom: 60px;
  }
</style>

<style>
  @import url('https://fonts.googleapis.com/css2?family=Work+Sans:wght@300&display=swap');  
  html {
    font-family: 'Work Sans', sans-serif;
  }

  #pageContainer{
      margin-top: 40px;
      flex-grow: 1;
      display: flex;
      flex-direction: column;
  }

  button{
    cursor: pointer;
  }

  #ContentTitle{
      width: fit-content;
      padding-bottom: 5px;
      border-bottom: 5px solid rgb(0, 102, 255);
      border-radius: 3px;
  }

  div{
    -webkit-tap-highlight-color: rgba(0,0,0,0);
    -webkit-tap-highlight-color: transparent;
  }
</style>
