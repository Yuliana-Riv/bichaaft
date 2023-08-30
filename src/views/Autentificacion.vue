<template>
  <div id="Autentificacion">
    <div class="content_login">
     
      <div class="B1">

        <div class="fondo-logo">
          <img src="../assets/Logo mo.png" alt="Logo sitio web">
          <p class="B1Text">Ingresa el código que fue enviado a tu correo electrónico</p>

        </div>

        <div class="B1F2">
            <div class="form_login">
              <form id="logincodeapp"  > 
                  <input 
                      id="code" 
                      v-model="code_form" 
                      type="text" 
                      name="code" 
                      required
                      placeholder="Código"
                  >
                  <input class="Vbuton" type="button"  @click="verify()" value="Verificar">
                  <p class="form-reenviar-codigo" >¿Problemas? <span class="span" @click="sendCode()"> Solicita un nuevo código aquí</span> </p>
                  
                  <p v-if="status=='error'" class="error-code">{{message}}</p>
              </form>
            </div>
        </div>
       
      </div>

      <div class="B2">
        <img class="B2" src="../assets/bichaBg mo.png">
      </div>

    </div>
  </div>
</template>
<script>


import userService from '../services/user.service'

export default {
  name: 'autentificacion',
  data: () => ({
    code_form: "",
    status:'',
    message:''
  }),
  created(){
 this.getIdentity()
  },
  computed:{
    identity() {
      return this.$store.getters['admin/getIdentity'];
    },
  },
  methods: {
      getIdentity: async function (){
          let response =  await this.$store.dispatch("admin/getData");
          return response
      },

      delMsg(){
        this.status='' 
        this.message=''
      },
       refresh: function () {
        setTimeout(() => this.delMsg(), 1500);
        },


    async  verify(){
        this.getIdentity()
        let identity= this.identity
      
   
          let code = String(identity.code)
          let id = String(identity.sub)

             let data ={
                "id":code,
                "id_user":id,
                "type":identity.role,
                "code":this.code_form
               
              }

                  

            let result = await this.$store.dispatch("main/addItem",  {option:'session', item:data});
                   
                  



          if(result.status == 'success'){
             let ath = await userService.createAuth();

             if(ath.status=='success'){
                 userService.setAth(ath.result);
                    
               this.$router.push("/administrador").catch(err => {});
             }else{
               this.status ='error'
               this.message='Ha ocurrido un error.'
                  this.refresh()
             }
             
            
       
             
          }else{
            this.status='error' 
            this.message='El codigo no coincide.'
             this.refresh()
          }
      },
      
     

     
      async sendCode() {
        
         this.getIdentity()
        let identity= this.identity
      try {
        

        await this.$store.dispatch("admin/resendCode", {
            email: identity.email,
            name: identity.name,
            code: identity.code
        });
        //console.log(identity.code);

         if(result.data.status !='success'){
             localStorage.removeItem('tkn')
             this.$router.push("/login").catch(err => {});
         }
       
      } catch (error) {
        this.status ='error'
      }
    }
  }
}
</script>


<style scoped>


  .message_error p{
     margin-bottom: 0vw !important;
     background:var(--color-1);
     border: 0vw;
     width: 19.46875VW;
     padding: .5vw;
     color: var(--color-4);
     font-weight: 400;
     text-align: center;
     font-size: 0.6333333333333334VW;
     font-style: normal;
      font-family: var(--Lato);
     margin-top:1.8229166666666667VW ;
     transition: all 300ms;

  }


.content_login {
    display: block;
}
.B1 {
  width: 100%;
  text-align: -webkit-center;
  margin-top: 12.564102564102564VW;
}
   #Login{
    
    background: #ffa400;
     background-repeat: no-repeat;
     background-size: 101%;
      font-family: var(--Lato);
   }

    .fondo-logo{
      background: white;
    }
      .fondo-logo img{
        width: 48.97435897435897VW;
        height: auto;
      }

   
.B1F2 {
  
}
   
p.error-code{
  color: var(--color-5);
}
   .logos_{
     display: flex;
   }

    .B1Text {
      width: 68vw;
      height: 8vw;
      color: #FA8433;
      font-weight: 500;
      font-size: 3.5897435897435894VW;
      font-family: var(--Lato);
      line-height:4.307692307692308VW;
      text-align: center;
      margin-bottom: 5.641025641025641VW !important;
      text-transform: uppercase;
      margin-top:11.8125vw;
    }

   .form_login form{
     display: inline-grid;
    justify-items: center;
   }

   

   .form_login  input{
     border-radius: 10vw;
     border: 0.052083333333333336VW solid #1E7E8B;
     width: 58.04871794871795VW;
     height: 12.86923076923077VW; 
     font-size: 3.3333333333333335VW;
      font-family: var(--Lato);
     color: var(--color-2);
     margin-bottom: 4.817948717948718VW !important;
   }

   

   .form_login input:first-child{
     margin-bottom: 1.0416666666666665VW;
   }

  .form_login ::placeholder{
    color: var(--color-2) !important;
    font-size: 3.3333333333333335VW;
    font-weight: 600;
  }

  .Vbuton {
       background: white;
    border: 0.052083333333333336vw solid #FA8433 !important;
    width: 70.048718VW !important;
    height: 12.86923076923077VW;
    color: #FA8433  !important;
    font-weight: 400;
    text-align: center;
    font-size: 3.3333333333333335VW;
    font-style: normal;
      font-family: var(--Lato);
    line-height: 1.0473958333333333VW;
    cursor: pointer;
    border-radius: 10vw;
    letter-spacing: 0.3vw;
  }
  .form-reenviar-codigo {
    color:#1E7E8B;
    font-weight:bold;
    margin-left:35vw;
    margin-right:35vw;
  }

  .span{
    color:#2DC7CA;
    text-align:center;
  }


  .B2 {
  width: 100%;
  height: 88.46153846153845VW;
  height:100%;
  display: block;
  background: white;
  margin-top: 33.230769230769234VW;
    
}
.B2 img {
  width:100VW;
  margin-top: -12.5vw;

 /* height: auto;
  float: right;
  margin-top: -12.5vw;
  z-index: 3;*/
}
.B0 {
  display: none;
}

.B1Text[data-v-38723cfa] {
   
    color: #FA8433;
    font-size: 0.9VW;
    font-family: var(--Lato);
    text-align: center;
    margin-bottom: 1VW !important;
    text-transform: uppercase;
    }


@media (min-width: 768px) {

  .message_error {
    display: flex;
     background:var(--color-1);
         width: 19.46875VW;
 margin-top:1.8229166666666667VW ;

  }
  .message_error p{
    margin-bottom: 0vw !important;
  
   
    border: 0vw;
  
    padding: 0.5vw 0vw;
    color: var(--color-5);
    font-weight: 400;
    text-align: center;
    font-size: 0.6333333333333334VW;
    font-style: normal;
    font-family: var(--font-titulo2);
   
    transition: all 300ms;
  }
  .message_error img {
       width: 1vw;
    height: 1vw;
    margin-top: 0.3vw;
  }

.B0 {
  display: block !important;
  width: 56.041666666666664VW;
  height: 56.25vw;
  display: block;
  background-image:"../assets/back pc.png";

  /*background: linear-gradient(90deg, #005cb9 0%, #ffa400 100%)*/
}
  

.B1 {
   /* width: 100%;*/
    width:26vw;
    height:50%;
    text-align: -webkit-center;
    margin-top: 12.552083333333334vw;
    border-radius:2vw;
    
  }

  .tl1{
    font-size:1.8229166666666667vw;
    margin-top:1vw;
  }
.content_login {
  display: flex !important;
  background-image: url(../assets/back_pc.png);
  background-size:cover;
  justify-content:center;


}
  .fondo-logo img {
    width: 14.21875VW;
    height: auto;
    margin-top: 5.90625VW;
    margin-bottom: 4.635416666666667VW;
  }

  .fondo-logo{
    background-color:white;
    border-radius:2vw;

  }
  .form_login form {
    display: inline-grid;
    justify-items: center;
    background-color:white;
    width: 25.937499999999998VW;
    border-radius:2vw;  
    margin-bottom: 12.552083333333334vw;
  }
  .form_login h1 {
    height: 4vw;

    font-weight: 500;
    font-size: 1.8229166666666667VW;
    line-height: 2.2916666666666665VW;
    text-align: center;
    margin-bottom: 1VW !important;
  }
  .form_login input {
    border-radius: 10vw;
    border: 0.052083333333333336VW solid #1E7E8B;
    width: 18.46875VW;
    height: 2.7083333333333335VW;
    font-size: 0.6770833333333334VW;
    color: var(--color-2) !important;
    margin-bottom: 1.875VW !important;
  }

  .form_login input:first-child{
    margin-bottom: 1.0416666666666665VW !important;
  }
  .form_login ::placeholder{
    color: #1E7E8B !important;
    font-size: 0.6770833333333334VW;
    font-weight: 600;
 }
 .form_login button {

    width: 15.989583333333332VW;
    height: 3.125VW;
    font-weight: 400;
    text-align: center;
    font-size: 0.7291666666666666VW;
    font-style: normal;
      font-family: var(--Lato);
    line-height: 1.0473958333333333VW;
    cursor: pointer;
    border-radius: 10vw;
    letter-spacing: 0.1vw;
    margin-bottom:1.0416666666666665vw;
  }

.B2{
  display:none; 

}
.B1Text{
  font-size:0.9375vw;
  text-align:center;
  width:18.28125vw;
  line-height:1vw;
  margin-top:2vw;
}

.form-reenviar-codigo {
    color:#1E7E8B;
    font-weight:bold;
    margin-left:5vw;
    margin-right:5vw;

  }

  .Vbuton {
   background: white;
    border: 0.052083333333333336vw solid #FA8433 !important;
    width: 15.989583333333332vw !important;
    height: 3.125vw;
    color: #FA8433  !important;
    font-weight: 400;
    text-align: center;
    font-size: 3.3333333333333335VW;
    font-style: normal;
    font-family: var(--Lato);
    line-height: 1.0473958333333333VW;
    cursor: pointer;
    border-radius: 10vw;
    letter-spacing: 0.3vw;
  }

}

</style>
