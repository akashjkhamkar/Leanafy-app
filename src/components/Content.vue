<template>
    <div id="Content">
        <span id="ContentTitle">
            Inbound Management
        </span>
        <Grid v-bind:GridItems="GridItems"/>
    </div>
</template>

<script>
    import Grid from "./Grid.vue"

    export default {
        name: "Content",
        components: {
            Grid
        },
        data: function() {
            return {
                GridItems: [{
                    text: "Upload",
                    boldtext: "New ARN",
                    img: "/images/file.png",
                    color: "blue",
                    id: 1
                },
                {
                    text: "Generate",
                    boldtext: "QR Code",
                    img: "/images/qrcode.png",
                    color: "black",
                    id: 2
                },
                {
                    text: "Item",
                    boldtext: "Scanning",
                    img: "/images/cube.png",
                    color: "green",
                    id: 3
                },
                {
                    text: "Initiate",
                    boldtext: "Put Away",
                    img: "/images/forklift.png",
                    color: "purple",
                    id: 4
                },
                {
                    text: "pink",
                    boldtext: "forklift",
                    img: "/images/forklift.png",
                    color: "magenta",
                    id: 5
                },
                {
                    text: "Initiate",
                    boldtext: "Put it Away!",
                    img: "/images/forklift.png",
                    color: "wheat",
                    id: 6
                },
                {
                    text: "Filler",
                    boldtext: "Fill it Away!",
                    img: "/images/forklift.png",
                    color: "wheat",
                    id: 7
                },
                {
                    text: "Filler",
                    boldtext: "Fill it Away!",
                    img: "/images/forklift.png",
                    color: "wheat",
                    id: 8
                }]
            }
        }
    }
</script>

<style scoped>
</style>
