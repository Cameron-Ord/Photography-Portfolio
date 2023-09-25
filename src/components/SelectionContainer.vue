<template>
  <div class="selectionContainer" v-if="TypeSelections !== undefined">
    <h4
      v-for="(type, i) in TypeSelections"
      :key="i"
      class="selectiontext"
      @click="getImages(i)"
      ref="SelectionButton"
    >
      {{ type }}
    </h4>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  data() {
    return {
      TypeSelections: ['Summer', 'Black/white']
    }
  },
  methods: {
    loadInitImages(index) {
      const selection = this.TypeSelections[index]
      const lowercased = selection.toLowerCase()
      axios({
        url: `${import.meta.env.VITE_APP_BASE_DOMAIN}/api/images`,
        params: {
          type: lowercased
        }
      })
        .then((response) => {
          this.$emit('response-data', response)
        })
        .catch((error) => {
          error
        })
    },
    getImages(i) {
      const button = this.$refs.SelectionButton[i].textContent
      const lowercased = button.toLowerCase()
      console.log(lowercased)
      axios({
        url: `${import.meta.env.VITE_APP_BASE_DOMAIN}/api/images`,
        params: {
          type: lowercased
        }
      })
        .then((response) => {
          this.$emit('response-data', response)
        })
        .catch((error) => {
          error
        })
    }
  },
  mounted() {},
  created() {
    this.loadInitImages(Math.floor(Math.random() * this.TypeSelections.length))
  }
}
</script>

<style lang="scss" scoped>
.selectionContainer {
  display: grid;
  width: 100%;
  align-items: center;
  justify-items: center;
  grid-template-columns: repeat(auto-fit, minmax(125px, 1fr));

  > .selectiontext {
    cursor: pointer;
  }
}
@media only screen and (min-width: 770px) {
  .selectionContainer {
    > .selectiontext {
      cursor: pointer;
    }
  }
}

@media only screen and (min-width: 1024px) {
  .selectionContainer {
    > .selectiontext {
      cursor: pointer;
    }
  }
}
</style>
