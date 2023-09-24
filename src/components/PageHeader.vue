<template>
  <nav class="headerNav">
    <div class="headerHome">
      <h2 class="homeIcon">Home</h2>
    </div>
  </nav>
</template>

<script>
export default {}
</script>

<style lang="scss" scoped>
.headerNav {
  display: grid;
  align-items: center;
  width: 100%;
  justify-items: center;
  > .headerHome {
    display: grid;
  }
}

@media only screen and (min-width: 770px) {
  .headerNav {
    > .headerHome {
    }
  }
}

@media only screen and (min-width: 1024px) {
}
</style>
