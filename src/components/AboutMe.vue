<template>
    <span class="aboutSpan">
        <h3 class="aboutHeaderText">About me</h3>
        <p class="aboutText">I'm Cameron, a Developer who loves photography, birds and music</p>
        <p class="aboutText">Most of the time with my photos I want to take interesting pictures of wildlife, but I generally photograph anything that interests me</p>
    </span>
</template>

<script>
    export default {
        
    }
</script>

<style lang="scss" scoped>
.aboutSpan{
    display: grid;
    align-items: center;
    justify-items: center;
    grid-template-rows: 0.5fr 1fr 1fr;

    >.aboutHeaderText{
        text-align: center;
    }
    >.aboutText{
        text-align: center;
        width: 85%;
        
    }
}

@media only screen and (min-width: 770px){
.aboutSpan{

    >.aboutHeaderText{
     
    }
    >.aboutText{
        text-align: center;
        width: 75%;
        
    }
}

}

@media only screen and (min-width: 1024px){

}
</style>