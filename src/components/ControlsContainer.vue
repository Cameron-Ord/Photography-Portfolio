<template>
    <div class="controlsContainer">
        <img src="/svgs/left.svg" alt="" class="leftArrow" ref="leftArrow">
        <img src="/svgs/right.svg" alt="" class="rightArrow" ref="rightArrow"> 
    </div>
</template>

<script>
    export default {
        
    }
</script>

<style lang="scss" scoped>
.controlsContainer{
    >.rightArrow{
        width: 25px;
    }
    >.leftArrow{
        width: 25px;
    }
}
</style>