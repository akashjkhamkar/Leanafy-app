<template>
    <div id="TopBar">
        <div id="TopBarCurrentPage">
            Inbound
        </div>
        <div id="TopBarRightSection">
            <div>
                <img id="bell" src="/images/bell.png" alt="">
            </div>
            <div>
                <img id="profile" src="/images/profile.jpeg" alt="">
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: "TopBar"
    }
</script>

<style scoped>
    #TopBar {
        display: flex;
        justify-content: space-between;
        align-items: center;
        padding-top: 10px;
        padding-bottom: 10px;
    }

    #TopBarRightSection {
        display: flex;
        justify-content: space-around;
        align-items: center;
        gap: 20px;
    }

    #profile{
        width: 40px;
        border-radius: 50%;
    }

    #bell {
        width: 23px;
    }
</style>