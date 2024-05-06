<script>
export default {
    name: 'AppFooter',

    data(){
        return{
            members:[
                {
                    nome: "Andrea",
                    cognome: "Livornese"
                },
                {
                    nome: "Alberto",
                    cognome: "Ferri"
                },
                {
                    nome: "Alessandro",
                    cognome: "Del Campo"
                }
            ],

            emails:[
                "andrealivornese@gmail.com",
                "falberto99@gmail.com",
                "alessandrodelcampo@gmail.com"
            ],

            socials:[
                "fa-facebook",
                "fa-x-twitter",
                "fa-instagram",
                "fa-google-plus-g",
                "fa-tiktok",
                "fa-youtube"
            ]
        }
    }
}
</script>


<template>

    <footer class="bg-body-tertiary">
        <div class="container py-5">


            <div id="footer-title">
              Mini progetto Boolean classe 118
            </div>

            <div class="row">

                <div class="col d-flex flex-column align-items-center ">

                    <div class="col-title">
                        Members
                    </div>

                    <div class="components">
                        <ul>
                            <li v-for="member in members">
                                <div class="name">
                                    {{ member.nome }}
                                </div>
                                <div class="last-name">
                                    {{ member.cognome }}
                                </div>
                            </li>
                        </ul>
                    </div>
                </div>

                <div class="col d-flex flex-column align-items-center">

                    <div class="col-title">
                        Contact
                    </div>

                    <div class="emails">
                        <ul>
                            <li v-for="email in emails">
                                {{ email }}
                            </li>
                        </ul>
                    </div>

                </div>

                <div class="col d-flex flex-column align-items-center">
                    <div class="col-title">
                        Social
                    </div>

                    <div id="social-grid">
                        <div v-for="social in socials" class="icon">
                            <i class="fa-brands" :class="social"></i>
                        </div>
                        
                    </div>
                </div>

            </div>
        </div>
        
        <hr>

        <div class="container py-4">
            <h6 class="text-center mb-3">
                La creazione di questi progetti sono  principalmente per scopo didattico, utili per la formazione sull'utilizzo delle nuove tecnologie di sviluppo web sotto la supervisione dei tutor di Boolean®. 
            </h6>

            <div id="copyright">
                Copyright© 2024, Boolean®. In caso di infrazione bisonga pagare millemila soldi in monete d'oro tassati del 2375432% dallo stato italiano.
            </div>
        </div>

    </footer>

</template>

<style lang="scss" scoped>


#footer-title{
    font-size:1.6em;
    font-weight: bold;
    text-align: center;

    margin-bottom: 20px;
}

.col-title{
    font-size:1.2em;
    font-weight: 600;   

    margin-bottom: 10px;
}

ul{
    margin: 0;
    padding: 0;
    
    display: flex;
    flex-direction: column;
    align-items:center;
    row-gap:5px;

    font-size: .8em;
    list-style-type: none;
    opacity: .8;
}

.components{

   

    li{

        display: flex;
        gap:8px;
        

        a{
            color:white;
            text-decoration: none;
        }
    }
  

}


#social-grid{

    max-width: 200px;

    display: flex;
    justify-content: center;
    flex-wrap: wrap;
    gap:10px;

    .icon{
        display: flex;
        justify-content: center;
        align-items: center;

        width: 50px;
        height: 50px;

        border:2px solid white;

        font-size:1.3em;

        transition: all .3s ease-in-out;

        
    }
    
    .icon:hover{

        background-color: white;

        color:black;

        cursor: pointer;

    }
   
}

#copyright{
    text-align: center;
    font-size: .7em;
    opacity: .8;
}




</style>