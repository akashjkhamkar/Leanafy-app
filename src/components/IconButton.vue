<template>
    <button>
        <img class="icon" v-bind:src="img" alt="icon">
    </button>
</template>

<script>
    export default {
        name: "IconButton",
        props: ["img"]
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
        background: black;
    }

    .icon{
        width: 30px;
    }
</style>