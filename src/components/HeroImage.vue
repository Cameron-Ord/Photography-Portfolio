<template>
  <span class="HeroImageSpan">
    <img src="../assets/redone.jpg" alt="" class="image" />
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
      height: 850px;
      object-fit: cover;
      width: 90%;
    }
  }
}
</style>
