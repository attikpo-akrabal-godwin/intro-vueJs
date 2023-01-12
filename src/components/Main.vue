<script >
    export default {
        emits:["showModalOnClick"],
        methods:{
            sendShowModalEvent(){
                this.$.emit("showModalOnClick")
            }
        }
    }
</script>

<template>
    <div class="container">
        <header>
            <div class="header-container">
                <div class="header-top">
                        <img src="../assets/icon.ico" class="logo" alt="logo">
                        <ul>
                            <li> <div class="detaille" >Détails de l'evenement</div> </li>
                            <li><a href="#">A Propos</a> </li>
                            <li> <a href="#">Contact</a></li>
                            <li> <a href="#">Evenements passées</a></li>
                        </ul>
                        <svg id="bar-svg" class="svg"  fill="#fe142f"  viewBox="0 0 448 512"><path d="M0 96C0 78.3 14.3 64 32 64H416c17.7 0 32 14.3 32 32s-14.3 32-32 32H32C14.3 128 0 113.7 0 96zM0 256c0-17.7 14.3-32 32-32H416c17.7 0 32 14.3 32 32s-14.3 32-32 32H32c-17.7 0-32-14.3-32-32zM448 416c0 17.7-14.3 32-32 32H32c-17.7 0-32-14.3-32-32s14.3-32 32-32H416c17.7 0 32 14.3 32 32z"/></svg>
                </div>
            </div>
            <div id="second-header" class="second-header">
                <span id="close-second-header" class="close-button">&times;</span>
                <ul>
                    <li> <a href="#">Détails de l'evenement</a>  </li>
                    <li> <a href="#">A Propos</a> </li>
                    <li> <a href="#">Contact</a></li>
                    <li> <a href="#">Evenements passées</a></li>
                </ul>
                
                
            </div>
        </header>
    
        <main >
            <div class="main-container">
                <div class="main-text" >
                    <h1 class="title">
                        Marathon national <br> de jeux vidéos
                    </h1>
                    <p class="body">
                        vous aimez jouer ? Notre prochain évenement gaming est ouvert aux réservations... Places limitées !
                    </p>
                    <button id="btn-a" class="btn-a" @click="sendShowModalEvent" > je M'inscris</button>
                </div>
    
                
                <div class="main-background-container">
                    <div class="black-background" >
        
                    </div>
        
                    <div class="image-background">
                        <img class="imageGame1" src="../assets/image2.jpg" alt="image d'un joueur ">
                    </div>
                </div>  
                <div class="btn-e-content">
                    <button id="btn-e" class="btn-e" @click="sendShowModalEvent" > je M'inscris</button>
                </div>  
            </div>
            
        </main>
        <footer class="footer">
            <div class="copyrigth" > copyrigth 2014 - 2022, GameOn inc</div>
        </footer>
    </div>
</template>

<style >
.container{
    width: 90%;
    margin: 0 auto;
}

header{
    width: 100%;
    position: relative;
    margin-bottom: 40px;
}
.second-header{
      display: none;  
}

.header-container {
    margin: 0 auto;
    width: 100%;
    padding-top: 10px;
}

.header-top{
    display: flex;
    width: 100%;
    justify-content: space-between;
    align-items: center;
}

.header-top ul li {
    display: inline-block;
    vertical-align: middle;
    margin-right: 5px;
}

.header-top ul li a{
    color: black;
    list-style: none;
    text-decoration: none;
}

.header-top .logo {
    height: 35px;
}

.detaille{
    background-color: #fe142f;
    border-radius: 5px;

    text-decoration: underline;
    display: flex;
    align-items: center;
    justify-content: center;
    text-align: center;
    width: 230px;
    height: 50px;
    color: white;
    font-size: 1.15em;
}

main{
    width: 100%;
    height: 600px;
    position: relative;
}

.main-container{
    width: 95%;
    height: 100%;
    margin-top: 0 auto;
}

.main-text{
    position: absolute;
    color: white;
    display: flex;
    flex-direction: column;
    justify-content: space-around;
    padding:0 4%;
    width: 100%;
    height: 100%;
    top: 0;
}
.title{
    font-size: 4em;
}
.body{
    width: 35%;
    font-size: 1.3em;
}

.btn-a{
    color: whitesmoke;
    background-color: #fe142f;
    width: 170px;
    height: 50px;
    border: none;
    border-radius: 5px;
    font-size: 1.15em;
    cursor: pointer;
}
.btn-b{
    color: whitesmoke;
    background-color: #fe142f;
    width: 100px;
    height: 40px;
    border: none;
    border-radius: 5px;
    font-size: 1.15em;
    margin: 0 auto;
    cursor: pointer;
}
.btn-e{
    display: none;
}
.main-background-container{
    display: flex;
    align-items: center;
    justify-content: center;
    height: 100%;
    border-radius: 0 0px 14px 0;
    box-shadow:  6px 6px  15px burlywood; 
    
}

.image-background{
    width: 60%  ;
    height: 100%;
}

.black-background{
    width: 40% ;
    height: 100%;
    background-color: #232323;
    border-radius: 12px 0 0 12px;
    object-fit: cover;
}

.imageGame1{
    width: 100% ;
    height: 100%;
    border-radius: 0 10px 12px 0;
    margin-left: 0;
    padding-left: 0;
    object-fit: cover;
    background: linear-gradient(blue, pink);
}


.copyrigth{
    margin-top: 5%;
    margin-left: 3%;
    color: #fe142f;
}
.svg{
    display: none;
}

@media (max-width: 768px ) {
    main{
        height: unset;
    }
   
    .modale-content{
        position: fixed;
        width: 100%;
        height: 95%;
        top:5%;
        left: unset;
        border-radius: 7px;
        background-color: #232323;
     }
    .main-container{
        width: 100%;
    }
    .header-top ul li {
        display: none;
    }
    .main-background-container{
        display: flex;
        align-items: center;
        justify-content: center;
        width: 100%;
        height: 60%;
        border-radius: 0 0px 14px 0;
        box-shadow:  6px 6px  15px burlywood; 
        
    }
    .black-background{
        display: none;
    }
    .image-background{
        width: 100%;
    }
    .imageGame1{
        border-radius: 12px 10px 12px 12px;
    }

    .main-text{
        position: relative;
        color: black;
        display: block;
        flex-direction: unset;
        justify-content: unset;
        padding:0 ;
        width: 100%;
        height: 30%;
        margin-bottom: 10%;
        top: 0;
    }
    .title{
        margin: 0 ;
        padding: 0;
        width: 100%;
        height: 70%;
        font-size: 2.5em;
    }
    .body{
        width: 100%;
        height: 30%;
        margin: 0;
        font-size: 1.3em;
    }
    .btn-a{
        display: none;
        cursor: pointer;
    }
    
    .btn-e{
        display: block;
        color: whitesmoke;
        background-color: #fe142f;
        width: 170px;
        height: 50px;
        border: none;
        border-radius: 5px;
        font-size: 1.15em;
        margin: 30px auto;
        cursor: pointer;
    }
    .footer{
        margin-top: 15%;
    }
    .copyrigth{
        width: 90%;
        margin: 30px auto ;
        color: #fe142f;
    }
    .second-header-collapse{
        display: block;
        background-color:#232323;
    }
    
    .second-header-collapse ul li a{
        text-decoration: none;
        color: #eee;
        font-size: 1.15em;
    
    }
    .second-header-collapse ul {
        list-style-type: none;
        padding: 0;
        margin: 0;
    }
    .second-header-collapse ul li{
        justify-content: center;
        text-align: center;
        width: 100%;
        height: 50px;
        border-bottom: 1px solid #eee;

    }
    .svg{
        display: block ;
        height: 40px;
        cursor: pointer;
    }
    
  }


</style>