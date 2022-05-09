<template>
<footer>
    <div class="text-center mt-4">
        Found {{len}} character
    </div>

</footer>
  
</template>

<script>
export default {
    name: 'FooterComponent',
    props: {
        len:Number
    }
}
</script>

<style lang="scss" scoped>

</style>