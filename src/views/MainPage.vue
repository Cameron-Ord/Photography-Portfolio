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
    </main>
</template>

<script>
import HeroImage from '../components/HeroImage.vue';
import HeroText from '../components/HeroText.vue';
import ImageSelector from '../components/ImageSelector.vue';
    export default {
        components:{
            ImageSelector,HeroText,HeroImage
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