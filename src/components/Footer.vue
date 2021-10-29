<template>
    <footer>
        <div id="footerbuttons">
            <PillButton 
            v-bind:isactive="activebutton === 1 ? true : false" 
            v-on:click.native="setactive(1)"
            text="Inbound"/>

            <IconButton 
            v-bind:isactive="activebutton === 2 ? true : false" 
            v-on:click.native="setactive(2)"
            lightimg="/images/lightbox.png"
            darkimg="/images/darkbox.png"/>

            <PillButton 
            v-bind:isactive="activebutton === 3 ? true : false" 
            v-on:click.native="setactive(3)"
            text="Outbound"/>
        </div>
    </footer>
</template>

<script>
    import PillButton from "./PillButton.vue"
    import IconButton from "./IconButton.vue"

    export default {
        name: "Footer",
        components: {
            PillButton,
            IconButton
        },
        methods: {
            setactive: function(id){
                if(this.activebutton === id){
                    return;
                }

                this.activebutton = id;
                this.$emit("isInbound", id)
            }
        },
        data: function() {
            return {
                activebutton : 1
            }
        }
    }
</script>

<style scoped>
    footer {
        display: flex;
        justify-content: center;
        align-items: center;
        position: fixed;
        bottom: 0;
        left: 0;
        right: 0;
        max-width: 100%;
        padding: 10px;
        background: white;
        border-top: 1px rgb(235, 235, 235) solid;
    }

    #footerbuttons{
        display: flex;
        justify-content: space-around;
        align-items: center;
        width: 100%;
        max-width: 400px;
    }
</style>
