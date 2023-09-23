<template>
    <article class="ImageContainer">
        <span class="containerSpan">
            <div class="imgContainer">
                <img :src="null" alt="">
            </div>
            <controls-container></controls-container>
            <selection-container></selection-container>
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