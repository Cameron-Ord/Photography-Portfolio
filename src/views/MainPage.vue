<template>
    <main class="pageMain">
        <section class="heroSection">
            <article class="heroArticle">
                <hero-image></hero-image>
                <hero-text></hero-text>
            </article>
        </section>
        <section class="imageSection">
            <image-selector></image-selector>
        </section>
        <section class="aboutSection">
            <about-me></about-me>
        </section>
        <section class="contactSection">
            <contact-me></contact-me>
        </section>
    </main>
</template>

<script>
import HeroImage from '../components/HeroImage.vue';
import HeroText from '../components/HeroText.vue';
import ImageSelector from '../components/ImageSelector.vue';
import AboutMe from '../components/AboutMe.vue';
import ContactMe from '../components/ContactMe.vue';
    export default {
        components:{
            ImageSelector,HeroText,HeroImage,AboutMe,ContactMe
        }
    }
</script>

<style lang="scss" scoped>
.pageMain{
    min-height: 100vh;
    display: grid;
    grid-template-rows: 1.25fr 0.35fr 1fr 1fr;
    >.heroSection{
        display: grid;
        >.heroArticle{
            display: grid;
            justify-items: center;
            grid-auto-flow: row;
            row-gap: 10px;

        }
    }
    >.imageSection{
        display: grid;
        justify-items: center;
        padding-top: 20px;
        padding-bottom: 20px;

    }
    >.aboutSection{
        display: grid;
        justify-items: center;


    }
    >.contactSection{
        display: grid;
        justify-items: center;
    }
}
@media only screen and (min-width: 770px){
    .pageMain{

    grid-template-rows: 1.25fr 0.35fr 1fr 1fr;
    >.heroSection{

        >.heroArticle{


        }
    }
    >.imageSection{

    }
    >.aboutSection{
 


    }
    >.contactSection{

    }
}
}

@media only screen and (min-width: 1024px){

}
</style>