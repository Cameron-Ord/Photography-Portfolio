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
    <section class="aboutSection contactSection">
      <about-me></about-me>
      <contact-me></contact-me>
    </section>
  </main>
</template>

<script>
import HeroImage from '../components/HeroImage.vue'
import HeroText from '../components/HeroText.vue'
import ImageSelector from '../components/ImageSelector.vue'
import AboutMe from '../components/AboutMe.vue'
import ContactMe from '../components/ContactMe.vue'
export default {
  components: {
    ImageSelector,
    HeroText,
    HeroImage,
    AboutMe,
    ContactMe
  }
}
</script>

<style lang="scss" scoped>
.pageMain {
  min-height: 100vh;
  display: grid;
  grid-auto-flow: row;
  row-gap: 50px;

  > .heroSection {
    display: grid;
    > .heroArticle {
      display: grid;
      justify-items: center;
      grid-auto-flow: row;
      row-gap: 25px;
    }
  }
  > .imageSection {
    display: grid;
    justify-items: center;
    align-items: center;

  }
  > .aboutSection {
    display: grid;
    justify-items: center;
    align-items: center;
    grid-template-rows: 1fr 1fr;

  }
  > .contactSection {
    display: grid;
    justify-items: center;
    align-items: center;

  }
}
@media only screen and (min-width: 770px) {
  .pageMain {
  row-gap: 100px;
   

    > .heroSection {
      > .heroArticle {
        row-gap: 50px;
      }
    }
    > .imageSection {
    }
    > .aboutSection {
    }
    > .contactSection {
    }
  }
}

@media only screen and (min-width: 1024px) {
  .pageMain {
    row-gap: 200px;

    align-items: center;
    > .heroSection {
      height: 850px;
      > .heroArticle {
        grid-template-columns: 1fr 2fr;
      }
    }
    > .imageSection {
      
    }
    > .aboutSection {
      grid-template-columns: 1fr 1fr;
      grid-template-rows: 1fr;
    }
    > .contactSection {

    }

  }
}
</style>
