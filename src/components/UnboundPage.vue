<template>
    <div id="UnboundPage">
        <span id="ContentTitle">
            Outbound Managment
        </span>
        <img src="/images/boat.jpg" alt="">
        <h3>Outbound Managment Console</h3>
    </div>
</template>

<script>
    export default {
        name: "UnboundPage"
    }
</script>

<style scoped>
    #UnboundPage{
        display: flex;
        flex-direction: column;
        gap: 10px;
    }

    img{
        width: 100%;
        border-radius: 10px;
    }
</style>