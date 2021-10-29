<template>
    <div id="InboundPage">
        <Content/>
        <MoreContent/>
    </div>
</template>

<script>
    import MoreContent from './MoreContent.vue'
    import Content from './Content.vue'
    export default {
        name: "InboundPage",
        components: {
            Content, 
            MoreContent
        }
    }
</script>

<style scoped>
    #InboundPage{
        display: flex;
        flex-direction: column;
        gap: 40px;
    }
</style>