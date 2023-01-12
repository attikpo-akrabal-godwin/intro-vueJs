<script scoped >
import Main from './components/Main.vue'
import Modale from './components/Modale.vue';
export default {
    components:{
        Main,
        Modale
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
    <Modale v-if="showModale" @showModalOnClick="toggle"/>
    <Main @showModalOnClick="toggle"/>
</template>

<style scoped >

</style>
