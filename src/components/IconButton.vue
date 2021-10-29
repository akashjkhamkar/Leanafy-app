<template>
    <button v-bind:class="{active: isactive}">
        <img class="icon" v-bind:src="isactive ? lightimg : darkimg" alt="icon">
    </button>
</template>

<script>
    export default {
        name: "IconButton",
        props: ["lightimg", "darkimg", "isactive"]
    }
</script>

<style scoped>
    button {
        width: 50px;
        height: 50px;
        display: flex;
        align-items: center;
        justify-content: center;
        border-radius: 50%;
        border-style: none;
        background: transparent;
    }

    .icon{
        width: 30px;
    }

    .active{
        background: rgb(0, 102, 255);
        color: white;
    }
</style>