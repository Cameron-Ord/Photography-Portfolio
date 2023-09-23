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
    grid-auto-flow: row;
    row-gap: 25px;
    >.aboutHeaderText{
        text-align: center;
    }
    >.aboutText{
        text-align: center;
        width: 85%;
    }
}
</style>