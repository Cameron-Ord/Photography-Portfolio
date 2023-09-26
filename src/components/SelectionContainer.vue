<template>
  <div class="selectionContainer" v-if="TypeSelections !== undefined">
    <div v-if="screenSize >= 1024">
      <h4
        v-for="(type, i) in TypeSelections"
        :key="i"
        class="selectiontext"
        @click="getImages(i)"
        ref="SelectionButton"
        @mouseover="Enlarge(this.$refs.SelectionButton[i])"
        @mouseleave="removeHighlight(this.$refs.SelectionButton[i])"
      >
        {{ type }}
      </h4>
    </div>
    <div v-if="screenSize < 1024">
      <h4
        v-for="(type, i) in TypeSelections"
        :key="i"
        class="selectiontext"
        @click="getImages(i)"
        ref="SelectionButton"
        @touchstart="Enlarge(this.$refs.SelectionButton[i])"
        @touchend="removeHighlight(this.$refs.SelectionButton[i])"
      >
        {{ type }}
      </h4>
    </div>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  data() {
    return {
      TypeSelections: ['Summer', 'Black/white'],
      screenSize: undefined
    }
  },
  methods: {
    handleResize() {
      console.log('handling resize...')
      this.screenSize = window.innerWidth
    },

    removeHighlight(ref) {
      ref.style.fontSize = ''
      ref.style.color = ''
    },

    Enlarge(ref) {
      if (this.screenSize >= 1024) {
        ref.style.fontSize = '1.75vw'
      } else if (this.screenSize < 1024) {
        ref.style.color = 'var(--green)'
      }
    },

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
    this.screenSize = window.innerWidth
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

  > div {
    width: 100%;
    display: grid;
    justify-items: center;
    align-items: center;
    grid-template-columns: repeat(auto-fit, minmax(125px, 1fr));
    > .selectiontext {
      cursor: pointer;
      margin-top: 4.5px;
      margin-bottom: 4.5px;
    }
  }
}
@media only screen and (min-width: 770px) {
  .selectionContainer {
    > div {
      display: grid;
      align-items: center;
      > .selectiontext {
        cursor: pointer;
        margin-top: 4.5px;
        margin-bottom: 4.5px;
      }
    }
  }
}

@media only screen and (min-width: 1024px) {
  .selectionContainer {
    > div {
      display: grid;
      align-items: center;
      > .selectiontext {
        cursor: pointer;
        margin-top: 4.5px;
        margin-bottom: 4.5px;
      }
    }
  }
}
</style>
