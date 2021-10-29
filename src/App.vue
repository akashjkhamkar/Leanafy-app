<template>
  <div id="megacontainer">
    <div id="subcontainer">
      <TopBar v-bind:current="getActivePage"/>
      <Hello/>

      <div id="pageContainer">
        <Inbound v-if="activePage === 1"/>
        <Box v-if="activePage === 2"/>
        <Unbound v-if="activePage === 3"/>
      </div>

      <Footer v-on:isInbound="changePage($event)"/>
    </div>
  </div>
</template>

<script>
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
        activePage: 1
      }
    },
    methods: {
      changePage: function(id){
        this.activePage = id;
      }
    },
    computed: {
        getActivePage() {
          if(this.activePage === 1){
            return "Inbound"
          }else if(this.activePage === 2){
            return "Box"
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
  @import url('https://fonts.googleapis.com/css2?family=Work+Sans:wght@300&display=swap');  html {
    font-family: 'Work Sans', sans-serif;
  }

  #pageContainer{
      margin-top: 40px;
      flex-grow: 1;
      display: flex;
      flex-direction: column;
  }


</style>

<style>
  button{
    cursor: pointer;
  }
</style>
