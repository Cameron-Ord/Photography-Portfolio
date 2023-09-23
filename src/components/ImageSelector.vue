<template>
    <article class="ImageContainer">
        <span class="containerSpan" v-if="Image_Holder !== undefined && Image_Holder.length !== 0">
            <div class="imgContainer">
                <img :src="Image_Holder[ImageIndex]" alt="" class="selectionImage">
            </div>
        </span>
        <span class="navSpan" v-if="Image_Holder !== undefined && Image_Holder.length !== 0">
            <controls-container @right-clicked="rightbutton" @left-clicked="leftbutton"></controls-container>
        </span>
        <span class="selectionSpan">
            <selection-container @response-data="HandleInput" class="selectionContainer"></selection-container>
        </span>
    </article>
</template>

<script>
import SelectionContainer from './SelectionContainer.vue';
import ControlsContainer from '../components/ControlsContainer.vue'
    export default {
        components:{
            ControlsContainer,SelectionContainer
        },
        data() {
            return {
                ImageIndex : 0,
                Image_Holder : undefined
            }
        },
        methods:{
            HandleInput(data){
                this.Image_Holder = []
                if(this.Image_Holder.length === 0){
                    for(let i = 0; i<data['data'].length; i++){
                        this.Image_Holder.push(data['data'][i]['file_path'])
                    }
                }

            },
            leftbutton(){
                this.ImageIndex--;
                if(this.ImageIndex < 0){
                    this.ImageIndex = this.Image_Holder.length - 1;
                }
            },
            rightbutton(){
                this.ImageIndex++;
                if(this.ImageIndex > this.Image_Holder.length - 1){
                    this.ImageIndex = 0;
                }
            },
        },
    }
</script>

<style lang="scss" scoped>
.ImageContainer{
    display: grid;
    width: 100%;
    

    >.navSpan{
        display: grid;
        align-items: center;
        justify-items: center;
    }

    >.selectionSpan{
        display: grid;
        align-items: center;
        justify-items: center;
    }

    >.containerSpan{
        display: grid;
        justify-items: center;
        >.imgContainer{
            display: grid;
            align-items: center;

            >.selectionImage{
                width: 100%;
                object-fit: cover;
            }
        }
    }
}

</style>