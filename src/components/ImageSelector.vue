<template>
    <article class="ImageContainer">
        <span class="containerSpan">
            <img src="/svgs/left.svg" alt="" class="leftArrow" ref="leftArrow">
            <div class="imgContainer">
                <img :src="null" alt="">
            </div>
            <img src="/svgs/right.svg" alt="" class="rightArrow" ref="rightArrow"> 
        </span>
    </article>
</template>

<script>
    export default {
        
    }
</script>

<style lang="scss" scoped>
.ImageContainer{
    display: grid;
    >.containerSpan{
        display: grid;

        >.imgContainer{

        }

        >.rightArrow{
            width: 25px;
        }
        >.leftArrow{
            width: 25px;
        }
    }
}

</style>