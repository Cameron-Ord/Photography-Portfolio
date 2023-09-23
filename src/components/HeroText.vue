<template>
    <span class="HeroTextSpan">        
        <h2 class="heroTextHeader">Welcome</h2>
        <p class="heroText">Hi there! I'm Cameron and this is my personal portfolio site where I upload my photos in a browsable format.</p>
        <p class="heroText">To view images simply just select a category and browse with the navigation arrows!</p>
    </span>
</template>

<script>
    export default {
        
    }
</script>

<style lang="scss" scoped>
.HeroTextSpan{
    display: grid;
    align-items: center;
    justify-items: center;
    grid-auto-flow: row;
    row-gap: 25px;
    padding-top: 5px;
    padding-bottom: 5px;

>.heroText{
    display: grid;
    text-align: center;
    width: 85%;
}
>.heroTextHeader{
    display: grid;
    text-align: center;
}
}
</style>