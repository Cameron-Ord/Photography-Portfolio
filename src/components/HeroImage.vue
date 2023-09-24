<template>
    <span class="HeroImageSpan">
        <img src="/siteimages/birdwp.JPG" alt="" class="image">
    </span>
</template>

<script>
    export default {
        
    }
</script>

<style lang="scss" scoped>
.HeroImageSpan{
    display: grid;
    justify-items: center;
    >.image{
        padding-top: 5px;
        padding-bottom: 5px;
        min-width: 100px;
        width: 100%;
        max-width: 770px;
    }
}

@media only screen and (min-width: 770px){
.HeroImageSpan{
    >.image{

        max-width: 1024px;
    }
}
}

@media only screen and (min-width: 1024px){

}
</style>