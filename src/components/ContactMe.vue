<template>
    <span class="contactSpan">
        <h3 class="contactHeaderText">Contact me</h3>
        <div class="subHeading">
            <p class="contactText">If you wish to contact me, feel free to add me on Discord!</p>
            <div class="socialLinks">
                <img src="/svgs/discord.svg" alt="" class="svgIcon">
            </div>
        </div>
        <div class="closingText">
            <p class="contactText">For professional inquiries: </p>
            <div class="professionLinks">
                <img src="/svgs/github.svg" alt="" class="svgIcon">
                <img src="/svgs/linkedin.svg" alt="" class="svgIcon">
            </div>
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
    grid-template-rows: 0.5fr 1fr 1fr;
    >.closingText{
        display: grid;
        justify-items: center;
        align-items: center;

        grid-template-rows: 75px 50px;
        width: 100%;
        >.professionLinks{
            display: grid;
            justify-items: center;
            grid-template-columns: repeat(auto-fit,minmax(50px,1fr));
            width: 60%;
        }
        >.contactText{
            text-align: center;
            width: 85%;
            
        }
    }
    >.subHeading{
        display: grid;
        justify-items: center;
        align-items: center;
        width: 100%;
        grid-template-rows: 75px 50px;
        >.socialLinks{
            display: grid;
            justify-items: center;
        }
        >.contactText{
            text-align: center;
            width: 85%;
        }
    }

}
</style>