<template>
    <div 
    class="ColouredIcon"
    v-bind:style="style">
        <img class="icon" v-bind:src="img" alt="icon">
    </div>
</template>

<script>
    export default {
        name: "ColouredIcon",
        props: ["color", "img"],
        computed: {
            style() {
                return "background: " + this.color;
            }
        }
    }
</script>

<style scoped>
    .ColouredIcon {
        width: 50px;
        height: 50px;
        display: flex;
        align-items: center;
        justify-content: center;
        border-radius: 5px;
    }

    .icon{
        width: 30px;
    }
</style>