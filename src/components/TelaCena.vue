<template>
    <div>
        <button @click="importaImagem"> 
        Oie 
        </button>
        <img :src="img">
        <!-- <img src="../assets/gaga.png"> -->
    </div>
</template>

<script>
export default {
    data(){
        return {
        img: '../assets/gaga.png',
        }
    },
    methods:{
        importaImagem(){

        }
    }
}
</script>

<style>

</style>