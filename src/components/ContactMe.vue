<template>
    <span class="contactSpan">
        <h3 class="contactHeaderText">Contact me</h3>
        <div class="subHeading">
            <p class="contactText">If you wish to contact me, feel free to add me on Discord!</p>
            <div class="socialLinks"></div>
        </div>
        <div class="closingText">
            <p class="contactText">For professional inquiries: </p>
            <div class="professionLinks"></div>
        </div>
    </span>
</template>

<script>
    export default {
        
    }
</script>

<style lang="scss" scoped>
.contactSpan{
    display: grid;
    align-items: center;
    justify-items: center;
    grid-auto-flow: row;
    row-gap: 25px;
    >.subHeading{
        display: grid;
        justify-items: center;
        width: 100%;

        >.socialLinks{

        }
        >.contactText{
            text-align: center;
            width: 85%;
        }
    }

    >.closingText{
        display: grid;
        justify-items: center;
        width: 100%;

        >.professionLinks{

        }
        >.contactText{
            text-align: center;
            width: 85%;
        }
    }
    >.contactHeaderText{
        
    }
}
</style>