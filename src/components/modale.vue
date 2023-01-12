<script scoped>
    import ModalForm from './ModalForm.vue'
    export default {
        emits:["showModalOnClick"],
        components:{
            ModalForm
        },
        methods:{
            sendShowModalEvent(){
                this.$.emit("showModalOnClick")
            },
            togleModalForm(){
                this.showModalForm = !this.showModalForm
            },
        },
        data(){
            return{
                showModalForm:true
            }
        }
    }
</script>

<template>
        <div id="modale" class="modale-container">
        <div class="modale-content">
            <span id="close"  class="close-button" @click="sendShowModalEvent">&times;</span>
            <div class="modal">
                <ModalForm v-if="showModalForm" @hideModalFormOnClick="togleModalForm" />
                <div v-else class="thanks-modale">
                    <div class="thanks">
                        Merci pour votre inscription
                    </div>
                    <button type="submit" id="btn-c" class="btn-b" @click="sendShowModalEvent" > fermer </button>
                </div>

            </div>
        </div>     
    </div>
</template>

<style scoped>
    .modale-container{
    position: fixed;
    left: 0;
    top: 0;
    bottom: 0;
    width: 100%;
    height: 100%;
    text-align: center;
    z-index: 1000;
    /* From https://css.glass */
    background: rgba(255, 255, 255, 0.15);
    border-radius: 16px;
    box-shadow: 0 4px 30px rgba(0, 0, 0, 0.1);
    backdrop-filter: blur(5.9px);
    -webkit-backdrop-filter: blur(5.9px);
}


.modale-content{
   position: fixed;
   width: 30%;
   height: 95%;
   top:3%;
   left: 39%;
   border-radius: 7px;
   background-color: #232323;
   z-index: 1005;
}
.modale {
    width: 100%;
    height: 100%;
    position: relative;
}
.thanks-modale {
   padding: 80% 0 ;
   justify-content: center;
   width: 100%; 
   
}
.thanks{
   color: white;
   width: 100%;
   height: 200px;
}
.close-button {
    float: right;
    width: 2rem;
    line-height: 1.7rem;
    font-size: large;
    text-align: center;
    cursor: pointer;
    border-radius: 30px;
    color: white;
  }
  .close-button:hover {
    background-color: rgba(255, 255, 255, 0.15);;
  }
  .svg{
    display: none;
  }

  @media (max-width: 768px ) {
    .modale-content{
        position: fixed;
        width: 100%;
        height: 95%;
        top:5%;
        left: unset;
        border-radius: 7px;
        background-color: #232323;
     }
  }

</style>