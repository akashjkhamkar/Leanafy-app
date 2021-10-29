<template>
    <div id="UnboundPage">
        <span id="ContentTitle">
            Unbound Managment
        </span>
        <img src="/images/boat.jpg" alt="">
        <h3>Unbound Managment Console</h3>
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

    #ContentTitle{
        width: fit-content;
        padding-bottom: 5px;
        border-bottom: 5px solid rgb(0, 102, 255);
        border-radius: 3px;
    }

</style>