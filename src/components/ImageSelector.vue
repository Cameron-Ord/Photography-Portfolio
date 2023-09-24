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
                let pageStyle = document.querySelector('.pageMain');
                let imageStyle = document.querySelector('.ImageContainer');
                pageStyle.style.gridTemplateRows = '1.35fr 1.25fr 1fr 1fr';
                imageStyle.style.gridTemplateRows= 'auto auto auto';
               
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
        >.imgContainer{
            display: grid;
            align-items: center;
            justify-items: center;
            position: relative;
            overflow: hidden;
            width: 100%;
            max-width: 100%;
            height: 0;
            padding-bottom: 75%;
            >.selectionImage{
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
@media only screen and (min-width: 768px){
    .ImageContainer{

    >.navSpan{

    }

    >.selectionSpan{

    }

    >.containerSpan{

        >.imgContainer{
            padding-bottom: 56.25%;


            >.imgContainer img{

            }

            >.selectionImage{

             
            
            }
        }
    }
}
}

@media only screen and (min-width: 1024px){

}
</style>