<template>
    <div class="componentSeperator">
  <article class="ImageContainer">
    <span class="containerSpan" v-if="Image_Holder !== undefined && Image_Holder.length !== 0">
      <div class="imgContainer">
        <img :src="Image_Holder[ImageIndex]" alt="" class="selectionImage" />
      </div>
    </span>
    <span class="navSpan" v-if="Image_Holder !== undefined && Image_Holder.length !== 0">
      <controls-container
        @right-clicked="rightbutton"
        @left-clicked="leftbutton"
      ></controls-container>
    </span>
    <span class="selectionSpan">
      <selection-container
        @response-data="HandleInput"
        class="selectionContainer"
      ></selection-container>
    </span>
  </article>
  <article class="DesktopImageContainer">
    <div class="desktopdivider">
        <span class="DesktopSelectionSpan">
            <selection-container
                @response-data="HandleInput"
                class="DesktopSelectionContainer"
            ></selection-container>
        </span>
        <span class="DesktopNavSpan" v-if="Image_Holder !== undefined && Image_Holder.length !== 0">
            <controls-container
                @right-clicked="rightbutton"
                @left-clicked="leftbutton"
            ></controls-container>
        </span>
    </div>
    <span class="DesktopContainerSpan" v-if="Image_Holder !== undefined && Image_Holder.length !== 0">
        <img :src="Image_Holder[ImageIndex]" alt="" class="selectionImage" />
    </span>
  </article>
    </div>
</template>

<script>
import SelectionContainer from './SelectionContainer.vue'
import ControlsContainer from '../components/ControlsContainer.vue'
export default {
  components: {
    ControlsContainer,
    SelectionContainer
  },
  data() {
    return {
      ImageIndex: 0,
      Image_Holder: undefined
    }
  },
  created(){

    window.addEventListener('resize', this.ModifyElements)

  },
  methods: {

    ModifyElements(){
        let imageStyle = document.querySelector('.ImageContainer')
        let desktopStyle = document.querySelector('.DesktopImageContainer');
        const screenWidth = window.innerWidth;
        if(screenWidth < 768){
        imageStyle.style.gridTemplateRows = '1fr 75px 50px'
      } else if (screenWidth >= 768 && screenWidth < 1024){
        imageStyle.style.gridTemplateRows = '1fr 75px 50px'
      } else if (screenWidth >= 1024){
        desktopStyle.style.gridTemplateColumns = '1fr 1.5fr';
      }

    },

    HandleInput(data) {
        this.Image_Holder = undefined
            if(this.Image_Holder === undefined){
                this.Image_Holder = []
                if (this.Image_Holder.length === 0) {
                    for (let i = 0; i < data['data'].length; i++) {
                    this.Image_Holder.push(data['data'][i]['file_path'])
                    }
 
                    this.ModifyElements()
                }
            }
            
    },
    leftbutton() {
      this.ImageIndex--
      if (this.ImageIndex < 0) {
        this.ImageIndex = this.Image_Holder.length - 1
      }
    },
    rightbutton() {
      this.ImageIndex++
      if (this.ImageIndex > this.Image_Holder.length - 1) {
        this.ImageIndex = 0
      }
    }
  }
}
</script>

<style lang="scss" scoped>

div{
    display: grid;
    align-items: center;

    width: 100%;

    >.DesktopImageContainer{
        display: none;
    }
    >.ImageContainer {
  display: grid;
  width: 100%;

  > .navSpan {
    display: grid;
    align-items: center;
    justify-items: center;
  }

  > .selectionSpan {
    display: grid;
    align-items: center;
    justify-items: center;
  }

  >.desktopContainerSpan{
    display: none;
  }

  > .containerSpan {
    display: grid;
    justify-items: center;

    > .imgContainer {
      display: grid;
      align-items: center;
      justify-items: center;
      position: relative;
      overflow: hidden;
      width: 100%;
      max-width: 100%;
      height: 0;
      padding-bottom: 76.25%;
      > .selectionImage {
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        object-fit: cover;
      }
    }
  }
}
}
@media only screen and (min-width: 768px) {
    div{

    >.DesktopImageContainer{
        display: none;
    }
  >.ImageContainer {
    > .navSpan {
    }

    > .selectionSpan {
    }

    > .containerSpan {
      > .imgContainer {
        padding-bottom: 56.25%;

        > .selectionImage {
        }
      }
    }
  }
}
}

@media only screen and (min-width: 1024px) {
    div{

        >.DesktopImageContainer{
            display: grid;
            grid-template-columns: 1fr;

            >.DesktopContainerSpan{
                    display: grid;
                    justify-items: center;
                    align-items: center;
                    position: relative;
                    overflow: hidden;
                    width: 95%;
                    max-width: 100%;
                    height: 0;
                    padding-bottom: 56.25%;
                    >img{
                        position: absolute;
                        top: 0;
                        left: 0;
                        width: 100%;
                        height: 100%;
                        object-fit: cover;
                    }
                }
            >.desktopdivider{
                display: grid;
                align-items: center;


                >.DesktopNavSpan{
                    display: grid;

                }

                >.DesktopSelectionSpan{
                    display: grid;

                }
            }
        }
      >.ImageContainer {
        display: none;

      }
    }
}
</style>
