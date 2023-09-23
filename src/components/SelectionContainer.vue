<template>
    <div class="selectionContainer" v-if="TypeSelections !== undefined">
        <h4 v-for="(type, i) in TypeSelections" :key="i" class="selectiontext" @click="getImages(i)" ref="SelectionButton">{{ type }}</h4>
    </div>
</template>

<script>
import axios from 'axios';
    export default {
        data() {
            return {
                TypeSelections: ['Summer', 'Black/white']
            }
        },
        methods:{
            getImages(i){
                const button = this.$refs.SelectionButton[i].textContent
                const lowercased = button.toLowerCase();
                console.log(lowercased)
                axios({
                    url: `${import.meta.env.VITE_APP_BASE_DOMAIN}/api/images`,
                    params:{
                        type: lowercased
                    }
                }).then((response)=>{
                    this.$emit('response-data', response);
                }).catch((error)=>{
                    error;
                })
            }
        },
        mounted(){

        }
    }
</script>

<style lang="scss" scoped>

</style>