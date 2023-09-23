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
    display: grid;
    >.heroSection{
        display: grid;

    }
}
</style>