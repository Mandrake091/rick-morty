//"https://api.sampleapis.com/rickandmorty/characters"
<template>
<section class="container">
    <loader-component v-if="loading"/>
        <div class="row">
            <div class="col-6 col-md-4 col-lg-3 gy-3" v-for="character in characterList" :key="character.id">
            <card-component :item="character"/>
            </div>
        </div>
  <footer-component :len="characterList.length"/>
</section>
</template>
<script>

import axios from 'axios';
import LoaderComponent from './LoaderComponent.vue';
import CardComponent from './CardComponent.vue';
import FooterComponent from './FooterComponent.vue';

export default {
    name: 'GridComponent',
    components: {
    LoaderComponent,
    CardComponent,
    FooterComponent
},
    data(){
        return {
            characterList: [],
            apiPath: 'https://api.sampleapis.com/rickandmorty/',
            loading: false
        }
    },
    mounted() {
        this.loading = true;
        axios.get(this.apiPath + 'characters').then((res)=>{
            this.characterList = res.data;
            this.loading = false
            console.log(this.characterList)
        }).catch((error) => {
            console.log(error)
        })
    }
}

</script>

<style lang="scss" scoped>

</style>