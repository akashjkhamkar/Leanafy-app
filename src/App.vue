<template>
  <div id="megacontainer">
    <div id="subcontainer">
      <TopBar v-bind:current="[Inbound ? 'Inbound' : 'Unbound']"/>
      <Hello/>

      <div id="pageContainer">
        <Inbound v-if="Inbound"/>
        <Unbound v-if="!Inbound"/>
      </div>

      <Footer v-on:isInbound="changePage"/>
    </div>
  </div>
</template>

<script>
  import TopBar from "./components/TopBar.vue"
  import Hello from "./components/Hello.vue"
  import Inbound from "./components/InboundPage.vue"
  import Unbound from "./components/UnboundPage.vue"
  import Footer from "./components/Footer.vue"

  export default {
    name: 'App',
    components: {
      TopBar,
      Hello,
      Footer,
      Inbound,
      Unbound
    },
    data: function() {
      return {
        Inbound: true
      }
    },
    methods: {
      changePage: function(){
        this.Inbound = !this.Inbound;
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
  }


</style>

<style>
  button{
    cursor: pointer;
  }
</style>
