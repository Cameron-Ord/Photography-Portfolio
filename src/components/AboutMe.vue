<template>
  <span class="aboutSpan">
    <h3 class="aboutHeaderText">About me</h3>
    <p class="aboutText">I'm Cameron, a Developer who loves photography, birds and music</p>
    <p class="aboutText">
      Most of the time with my photos I want to take interesting pictures of wildlife, but I
      generally photograph anything that interests me
    </p>
  </span>
</template>

<script>
export default {}
</script>

<style lang="scss" scoped>
.aboutSpan {
  display: grid;
  align-items: center;
  justify-items: center;
  grid-auto-flow: row;
  row-gap: 50px;

  > .aboutHeaderText {
    text-align: center;
  }
  > .aboutText {
    text-align: center;
    width: 75%;
    padding: 10px;
    max-width: 500px;
  }
}

@media only screen and (min-width: 770px) {
  .aboutSpan {
    width: 100%;
    height: 500px;
    grid-auto-flow: row;
    row-gap: 0px;
    grid-template-rows: 100px 200px 200px;
    > .aboutHeaderText {
    }
    > .aboutText {
      text-align: center;
      width: 60%;
    }
  }
}

@media only screen and (min-width: 1024px) {
  .aboutSpan {
    width: clamp(500px, 100%, 800px);
    max-width: 800px;
    height: 500px;
    grid-template-rows: 100px 200px 200px;

    > .aboutHeaderText {
    }
    > .aboutText {
      text-align: center;
      width: 60%;
    }
  }
}
</style>
