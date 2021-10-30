<template>
    <div id="ComponentGrid">

        <div id="grid">
            <div 
            class="GridItem"
            v-for="item in GridItems"
            v-bind:key="item.id">
                <ColouredIcon 
                v-bind:color="item.color"
                v-bind:img="item.img"/>

                <div class="description">
                    <span>{{item.text}}</span>
                    <h3>{{item.boldtext}}</h3>
                </div>
            </div>
        </div>

    </div>
</template>

<script>
    import ColouredIcon from "./ColouredIcon.vue" 
    export default {
        name: "Grid",
        props: ["GridItems"],
        components: {
            ColouredIcon
        }
    }
</script>

<style scoped>

    #ComponentGrid{
        margin-top: 20px;
        display: flex;
        justify-content: center;
        align-items: center;
    }

    #grid{
        display: grid;
        grid-gap: 10px;
        grid-template-rows: auto auto;
        justify-items: center;
        width: 290px;
        grid-auto-flow: column;
        overflow-x: scroll;
        border-radius: 10px;
        padding-bottom: 20px;
    }

    .GridItem{
        width: 100px;
        height: 100px;
        border-radius: 10px;
        padding: 20px;
        background: rgb(235, 235, 235);
    }

    .description{
        margin-top: 20px;
        font-size: 15px;
    }

    h3{
        margin-top: 0;
    }

    #grid::-webkit-scrollbar {
        height: 5px;
        width: 50px;
    }
    
    #grid::-webkit-scrollbar-track {
        background-color: rgb(233, 233, 233);
    }

    #grid::-webkit-scrollbar-thumb {
        background-color: #0066ff;
        outline: 1px solid slategrey;
    }

</style>