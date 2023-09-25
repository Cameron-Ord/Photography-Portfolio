<template>
  <span class="HeroImageSpan">
    <img src="/siteimages/birdwp.JPG" alt="" class="image" />
  </span>
</template>

<script>
export default {}
</script>

<style lang="scss" scoped>
.HeroImageSpan {
  display: grid;
  justify-items: center;
  align-items: center;
  > .image {
    min-width: 100px;
    width: 100%;
    height: 100%;
    object-fit: cover;
    max-width: 770px;
    padding-top: 7.5px;
    padding-bottom: 7.5px;
  }
}

@media only screen and (min-width: 770px) {
  .HeroImageSpan {
    > .image {
      max-width: 1024px;
    }
  }
}

@media only screen and (min-width: 1024px) {
  .HeroImageSpan {
    > .image {
      height: 100%;
      object-fit: cover;
      width: 90%;
    }
  }
}
</style>
