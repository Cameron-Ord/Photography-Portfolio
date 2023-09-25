<template>
  <div class="controlsContainer">
    <img src="/svgs/left.svg" alt="" class="leftArrow" ref="leftArrow" @click="leftarrow" @mouseover="setColor(this.$refs.leftArrow)"/>
    <img src="/svgs/right.svg" alt="" class="rightArrow" ref="rightArrow" @click="rightarrow" @mouseover="setColor(this.$refs.rightArrow)"/>
  </div>
</template>

<script>
export default {
  data() {
    return {}
  },
  methods: {

    setColor(tag){
      console.log(tag)
    },

    leftarrow() {
      this.$emit('left-clicked')
    },

    rightarrow() {
      this.$emit('right-clicked')
    }
  }
}
</script>

<style lang="scss" scoped>
.controlsContainer {
  display: grid;
  align-items: center;
  justify-items: center;
  grid-template-columns: 1fr 1fr;
  width: 90%;
  max-width: 350px;
  padding-top: 25px;
  > .rightArrow {
    width: 50px;
  }
  > .leftArrow {
    width: 50px;
  }
}

@media only screen and (min-width: 770px) {
  .controlsContainer {
    > .rightArrow {
      width: 50px;
    }
    > .leftArrow {
      width: 50px;
    }
  }
}

@media only screen and (min-width: 1024px) {
  .controlsContainer {
    max-width: none;
    width: 100%;
    > .rightArrow {
      width: 50px;
    }
    > .leftArrow {
      width: 50px;
    }
  }
}
</style>
