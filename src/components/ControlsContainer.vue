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
    display: grid;
    align-items: center;
    justify-items: center;
    grid-template-columns: 1fr 1fr;
    width: 90%;
    max-width: 350px;
    height: 50px;
    >.rightArrow{
        width: 25px;
    }
    >.leftArrow{
        width: 25px;
    }
}
</style>