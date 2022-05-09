<template>
<div>
    <div class="input-group">
        <select class="border-white" name="genre" id="genre" v-model="inputText" @change="changeSearch">
            <option value="">All</option>
            <option :value="specie" v-for="specie in characterSpecies" :key="specie">{{specie}}</option>
        </select> 
        <input type="text" class="form-control" placeholder="Search" v-model='inputText' @keyup.enter="search">
        <button class="btn btn-success" type="button" @click="search">Search</button>
        <button class="btn btn-danger" type="button"  @click="reset">Reset</button>

    </div>
</div>
</template>
<script>
export default {
    name:'SearchBar',
    data(){
        return{
            inputText:'',
        }
    },
    props:['characterSpecies'],
    methods:{  
        reset(){
            this.inputText='';
            this.$emit('mySearch',this.inputText)
        },
        search(){
            this.$emit('mySearch',this.inputText)
           
        },
        changeSearch(){
             this.$emit('mySearch',this.inputText)
        }
    }
}
</script>

<style lang="scss" scoped>
select{
    background: transparent;
}

</style>