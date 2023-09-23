<template>
    <article class="ImageContainer">
        <span class="containerSpan">
            <div class="imgContainer">
                <img :src="null" alt="">
            </div>
            <controls-container @right-clicked="rightbutton" @left-clicked="leftbutton"></controls-container>
            <selection-container @response-data="HandleInput"></selection-container>
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

        methods:{
            HandleInput(data){
                console.log(data)
            },
            leftbutton(data){
                console.log('left works',data)
            },
            rightbutton(data){
                console.log('right works',data)
            },
        },

        data() {
            return {
                Image_Holder: undefined
            }
        },
    }
</script>

<style lang="scss" scoped>
.ImageContainer{
    display: grid;
    >.containerSpan{
        display: grid;
        justify-items: center;
        >.imgContainer{

            >img{

            }
        }
    }
}

</style>