<template>
    <div class="controlsContainer">
        <img src="/svgs/left.svg" alt="" class="leftArrow" ref="leftArrow" @click="leftarrow">
        <img src="/svgs/right.svg" alt="" class="rightArrow" ref="rightArrow" @click="rightarrow"> 
    </div>
</template>

<script>
    export default {
        data() {
            return {
                
            }
        },
        methods:{
            leftarrow(){
                this.$emit('left-clicked');
            },

            rightarrow(){
                this.$emit('right-clicked');
            },
        }
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