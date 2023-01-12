<script>
    let initForm = {
                prenom:"",
                prenomError:"",
                nom:"",
                nomError:"",
                email:"",
                emailError:"",
                naissance:"",
                naissanceError:"",
                nbr:"",
                nbrError:"",
                tournois:"",
                tournoisError:"",
                lu:true,
                luError:"",
                prevenu:false,
                prevenuError:""
            }
    export default {
        emits:['hideModalFormOnClick','closeModal'],
        methods:{
            handleSubmit(e){
                e.preventDefault()
            },
            sendHideModalFormOnClick(){
                this.$.emit('hideModalFormOnClick')
            },
            handleOnclickSubmitButton(e){
                e.preventDefault()
                let isvalide = true 
                const rePren = new RegExp('[0-9]')
                if ((this.form.prenom.length<3||(rePren.test(this.prenom)))) {
                    this.form.prenomError = "prénom doit avoir plus de 3 caractères et ne contenant pas de chiffre"
                    isvalide=false
                }else{
                    this.form.prenomError = ''
                }

                const reNom = new RegExp('[0-9]')
                if ((this.form.nom.length<3||(reNom.test(nom.value)))) {
                    this.form.nomError = "le nom doit avoir plus de 3 caractères et ne contenant pas de chiffre"
                    isvalide=false
                }else{
                    this.form.nomError =""
                }

                if (!/^[\w-\.]+@([\w-]+\.)+[\w-]{2,4}$/g.test(this.form.email)) {
                    this.form.emailError = "email non valide"
                    isvalide=false
                }else{
                    this.form.emailError = ""
                }

                if(!this.form.naissance){
                    this.form.naissanceError = "veillez renseigner votre date de naissance "
                    isvalide=false
                }else{
                    this.form.naissanceError = ""
                }
                if (!this.form.nbr) {
                    this.form.nbrError = "veillez renseigner votre nombre de participation"
                    isvalide=false
                }else{
                    this.form.nbrError = ""
                }

                if (!this.form.lu) {
                    this.form.luError = "veillez aprouver"
                    isvalide=false
                }else{
                    this.form.luError = ""
                }
                if (!this.form.tournois) {
                    this.form.tournoisError = "veillez choisir une ville"
                    isvalide=false
                }

                if (isvalide) {
                    this.form = Object.assign({}, initForm)
                    this.sendHideModalFormOnClick()
                }
                
            }
        },
        data(){
            return{form:Object.assign({}, initForm)} 
        } 
    }
</script>


<template>
            <form id="modale-form" name="modale-form" class="modale-form"  @submit.prevent="handleSubmit" >
                    <label class="label-text" for="prenom">
                        Prénom  
                        <input  v-model="form.prenom" class="inpuText" type="text"> 
                        <span v-if="form.prenomError" class="error red" id="prenom-error">{{ form.prenomError }}</span>
                    </label> 
                    <label class="label-text" for="nom">
                        Nom 
                        <input name="nom" id="nom" v-model="form.nom" class="inpuText" type="text">
                        <span v-if="form.nomError" class="error red" id="nom-error">{{ form.nomError }}</span>
                    </label> 
                    <label class="label-text" for="email">
                        E-mail 
                        <input name="email" id="email" v-model="form.email" class="inpuText" type="email">
                        <span v-if="form.emailError" class="error red" id="email-error">{{ form.emailError }}</span>
                    </label> 
                    <label class="label-text" for="naissance">
                        Date de naissance  
                        <input name="naissance" id="naissance" v-model="form.naissance" class="inpuText" type="Date">
                        <span v-if="form.naissanceError" class="error red" id="naissance-error">{{ form.naissanceError }}</span> 
                    </label> 
                    <label class="label-text" for="nbr">
                         A comnbien de tournois GomeOn avez-vous déja participé ? 
                         <input name="nbr" id="nbr" v-model="form.nbr" class="inpuText" type="number"> 
                         <span v-if="form.nbrError" class="error red" id="nbr-error">{{ form.nbrError }}</span> 
                    </label> 
                    <label class="label-text"  >
                        A quel tournois souhaitez-vous participer cette année ?  
                    </label>
                    <div class="radio-group"  >
                            <label class="label-radio" for="tournois1"> 
                                <input class="imput-radio" name="tournois" v-model="form.tournois"  id="tournois1"  value="1" type="radio" > 
                                New York
                            </label>
                            <label class="label-radio" for="tournois2"> 
                                <input class="imput-radio" name="tournois" v-model="form.tournois"  id="tournois2" value="2" type="radio" > 
                                San Francisco
                            </label> 
                            <label class="label-radio" for="tournois3"> 
                                <input class="imput-radio" name="tournois" v-model="form.tournois"  id="tournois3" value="3" type="radio" > 
                                SeaTeal 
                            </label> 
                            <label class="label-radio" for="tournois4"> 
                                <input class="imput-radio" name="tournois" v-model="form.tournois"  id="tournois4" value="4" type="radio" > 
                                Chicago 
                            </label> 
                            <label class="label-radio" for="tournois5"> 
                                <input class="imput-radio" name="tournois" v-model="form.tournois"  id="tournois5" value="5" type="radio" > 
                                Ecotan
                            </label> 
                            <label class="label-radio" for="tournois6"> 
                                <input class="imput-radio" name="tournois" v-model="form.tournois"  id="tournois6" value="6" type="radio" > 
                                Portland 
                            </label>   
                                   
                    </div>
                    <span v-if="form.tournoisError" class="error red" id="tournois-error">{{ form.tournoisError }}</span> 

                    
                    <div class="checkbox-group">
                        <label  class="label-checkbox">
                            <input type="checkbox" v-model="form.lu" class="input-checkbox" checked name="lu" id="lu" >
                            j'ai lu et j'aprouve les conditions 
                        </label>
                    
                        <label for="prevenu" class="label-checkbox">
                            <input type="checkbox" v-model="form.prevenu" class="input-checkbox" name="prevenu" id="prevenu" >
                            je souhaite etre  prévenue des prochains evenements
                        </label>
                        <span v-if="form.luError" class="error red" id="lu-error">{{ form.luError }}</span> 
                    </div>
                    <div class="button-group" >
                        <button id="btn-b" class="btn-b" @click="handleOnclickSubmitButton"> c'est parti </button>
                    </div>
            </form>
</template>

<style  >
    .modale-form {
    /*margin-top: 6%;*/
    /*padding: 0 5%;*/
    margin: 6% auto;
    justify-content: start;
    width: 90%; 
}


.inpuText {
    display: block;
    width: 100%;
    height: 40px;
    border-radius: 5px;
    margin-top: 2%;
    padding: 0;
    border: none;
}
.error{
    
    display: none;
}

.red{
    color: #fe142f;
    font-size: .9em;
    display: block;
}

.label-text {
    display: block;
    text-align:start ;
    width: 100%;
    color: white;
    font-size: .7em;
}
.label-radio{
    color: white;
    font-size: .8em;
    display: flex;
    align-items: center;
    height: 15%;
    cursor: pointer;
    
}

.imput-radio{
    color: white;
    width: 20px;
    height: 20px;
    cursor: pointer;
}
.imput-radio:checked{
    background-color: red;
}
.checkbox-group{
    display: flex;
    flex-direction: column;
    width: 100%;
    height: 6%;
}

.imput-checkbox{
    width: 0px;
    height: 0px; 
    cursor: pointer;
}
.checkmark{
    height: 25px;
    width: 25px;
    background-color: #eee;
}
.label-checkbox{
    display: flex;
    text-align: start;
    color: white;
    padding-bottom: 2%;
}
.button-group{
    display: flex;
    text-align: center;
    
}

.radio-group{
    display: flex;
    flex-wrap: wrap;
    align-items: center;
    width: 100%;
    margin-bottom: 5%;
}
</style>