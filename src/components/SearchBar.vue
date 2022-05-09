<template>
<div>
    <div class="input-group">
        <input type="text" class="form-control" placeholder="Recipient's username" aria-label="Recipient's username with two button addons" v-model='inputText' @keyup.enter="search">
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
    methods:{  
        reset(){
            this.inputText='';
            this.$emit('mySearch',this.inputText)
        },
        search(){
            this.$emit('mySearch',this.inputText)
            this.inputText='';
        }
    }
}
</script>

<style lang="scss" scoped>

</style>