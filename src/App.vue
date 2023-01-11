<script >
import first from './components/first.vue'
import modale from './components/modale.vue';
export default {
    components:{
        first,
        modale
    },
    data(){
        return {
            showModale:false
        }
    },
    methods:{
        toggle(){
            this.showModale = !this.showModale ;
        }
    }
}
</script>

<template>
    <modale v-if="showModale" @showModalOnClick="toggle"/>
    <first @showModalOnClick="toggle"/>
</template>

<style >
html ,body{
    max-width: 1440px;
    font-family: Verdana;
    overflow-x: hidden;
    margin: 0  auto ;
}
</style>
