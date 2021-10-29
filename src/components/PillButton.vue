<template>
    <button v-bind:class="{active : isactive}">
        {{text}}
    </button>
</template>

<script>
    export default {
        name: "PillButton",
        props: ["text", "isactive"]
    }
</script>

<style scoped>
    button {
        height: 40px;
        display: flex;
        align-items: center;
        justify-content: center;
        border-style: none;
        border: 1px transparent solid;
        padding: 15px;
        border-radius: 50px;
        background: transparent;
        color: rgb(104, 104, 104);
    }

    .active{
        background: rgb(0, 102, 255);
        color: white;
    }
</style>