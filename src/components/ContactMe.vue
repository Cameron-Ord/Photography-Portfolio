<template>
  <span class="contactSpan">
    <h3 class="contactHeaderText">Contact me</h3>
    <div class="subHeading">
      <p class="contactText">If you wish to contact me, feel free to add me on Discord!</p>
      <div class="socialLinks">
        <img src="/svgs/discord.svg" alt="" class="svgIcon" />
      </div>
    </div>
    <div class="closingText">
      <p class="contactText">For professional inquiries:</p>
      <div class="professionLinks">
        <img src="/svgs/github.svg" alt="" class="svgIcon" />
        <img src="/svgs/linkedin.svg" alt="" class="svgIcon" />
      </div>
    </div>
  </span>
</template>

<script>
export default {}
</script>

<style lang="scss" scoped>
.contactSpan {
  display: grid;
  align-items: center;
  justify-items: center;
  grid-template-rows: 50px 1fr 1fr;
  > .closingText {
    display: grid;
    justify-items: center;
    align-items: center;
    width: 100%;
    grid-template-rows: 1fr 1fr;

    > .professionLinks {
      display: grid;
      justify-items: center;
      grid-template-columns: repeat(auto-fit, minmax(35px, 1fr));
      width: 40%;
    }
    > .contactText {
      text-align: center;
      width: 75%;
      padding: 10px;
    }
  }
  > .subHeading {
    display: grid;
    justify-items: center;
    align-items: center;
    width: 100%;

    grid-template-rows: 1fr 1fr;
    > .socialLinks {
      display: grid;
      justify-items: center;
    }
    > .contactText {
      text-align: center;
      width: 75%;
      padding: 10px;
    }
  }
}
@media only screen and (min-width: 770px) {
  .contactSpan {
    width: 100%;

    > .closingText {
      > .professionLinks {
        width: 25%;
      }
      > .contactText {
        width: 60%;
      }
    }
    > .subHeading {
      > .socialLinks {
      }
      > .contactText {
        width: 60%;
      }
    }
  }
}

@media only screen and (min-width: 1024px) {
  .contactSpan {
    width: 100%;
    height: 500px;
    > .closingText {
      > .professionLinks {
        width: 25%;
      }
      > .contactText {
        width: 60%;
      }
    }
    > .subHeading {
      > .socialLinks {
      }
      > .contactText {
        width: 60%;
      }
    }
  }
}
</style>
