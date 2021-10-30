<template>
    <div id="UnboundPage">
        <span id="ContentTitle">
            Boredom Management
        </span>

        <div id="text">
            <h2>Bored ?</h2>
        </div>
        <PillButton
        text="Get a suggestion"
        isactive="true"
        v-on:click.native="getSuggestion"/>

        <img 
        v-if="loading"
        src="/images/loading.gif" alt="loading..."/>
        <h3 v-else>{{suggestion}}</h3>
    </div>
</template>

<script>
    import axios from "axios"
    import PillButton from "./PillButton.vue"
    export default {
        name: "UnboundPage",
        components: {
            PillButton
        },
        data: function(){
            return {
                suggestion: "",
                loading: false
            }
        },
        methods: {
            getSuggestion: function(){
                this.loading = true;
                axios.get("https://www.boredapi.com/api/activity/")
                .then(res => {
                    this.suggestion = res.data.activity;
                    this.loading = false;
                })
                .catch(() => {
                    alert("something went wrong")
                })
            }
        }
    }
</script>

<style scoped>
    #UnboundPage{
        flex-grow: 1;
        display: flex;
        flex-direction: column;
        align-items: center;
        gap: 10px;
    }

    img{
        width: 100%;
        border-radius: 10px;
    }

    button{
        padding: 10px;
        width: fit-content;
    }

    #text{
        text-align: center;
    }

    h2 {
        margin-bottom: 10px;
    }

    h3{
        text-align: center;
        margin-top: 10vh;
    }
</style>