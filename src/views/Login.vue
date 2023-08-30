<template>
    <div class="login" id="Login">
      <div class="content_login">

        <div class="B1">

          <div class="fondo-logo">
            <img src="../assets/Logo mo.png" alt="Logo sitio web">

            <h2 class="tl1">LOGIN</h2>

          </div>

          <div class="B1F2">
            <div class="form_login">
              <form @submit.prevent="
                  login(
                    email,
                    password
                  )
                ">
                <input v-model="email" type="email" name="email" id="email"  :placeholder="'Correo electrónico'" required>
                <input v-model="password" type="password" name="pass" id="pass" minlength="8" :placeholder="'Contraseña'" required>

                <button  variant="outline-secondary" type="submit">INICIAR SESIÓN</button>


                <div  class="message_error" v-if="status=='error'">
                    <p>
                      {{this.message}}
                    </p>
                    <img src="../assets/default/alert.png">
                </div>
              </form>
            </div>
          </div>

        </div>

        <div>
          <img class="B2" src="../assets/bichaBg mo.png">

        </div>
        
         
       </div>
    </div>
</template>
<script>

import userService from '../services/user.service'

export default {
  name: 'Login',
  data() {
    return {
      status:'',
      message:'',
      email:'',
      password:''

    };
  },
  metaInfo() {
    return {
      title: "Login",
      titleTemplate: "%s | Coyotas Lourdes",
      htmlAttrs: {
        lang: "es",
      },
      meta: [
        { charset: "utf-8" },
        {
          name: "description",
          content:
            "Coyotas Lourdes.",
        },
        { name: "viewport", content: "width=device-width, initial-scale=1" },
      ],
    };
  },
  computed:{
  
    identity() {
      return this.$store.getters['admin/getIdentity'];
    }
  },

  methods:{
      wait: function () {
      setTimeout(() => this.$router.go(), 200);
    },
     delStatus: function () {
      setTimeout(() => this.delMsgs()
      ,1500);
    },
    delMsgs: function(){
       this.status=""
       this.message=""
    },
     async login(email, password) {
       this.status =''
       this.message =''

        let result = await this.$store.dispatch("admin/login",  {email, password});
      
         if(result.status=='success'){

          let response = await this.$store.dispatch("admin/getData");

     
              
          if(response.status =='success'){

            if(response.result.role =='legrafica' || response.result.role =='admin'){
                let isAdmin =  userService.isAdmin(response.result)
        

                if(isAdmin.admin == true){ // para el administrador
                        this.$router.push("/auth").catch(err => {});
                }else{ 
                      this.wait()  
                }


              }else{
                 this.$router.push("/").catch(err => {});
              }

                

          }else{
             this.status='error'
              this.message = response.message
              this.delStatus()
              this.wait()
          } 
        
         
        

         

        }else{
          this.status='error'
          this.message = result.message
          this.delStatus()
        }
        
     }
  }
}
</script>
<style scoped>

  .message_error {
    display: flex;
     background:var(--color-1);
       margin-top: 3.8229166666666667VW ;
        border-radius: 10vw;
         width: 69.04871794871795VW;
  }
  .message_error p{
    margin-bottom: 0vw !important;
    margin-top: 0vw;
    border: 0vw;
    width: 90%;
    padding: 2.5vw 0vw;
    color: var(--color-5);
    font-weight: 400;
    text-align: center;
    font-size: 3.3333333333333335VW;
    font-style: normal;
    font-family: var(--font-titulo2);
  
   
    transition: all 300ms;
  }
  .message_error img {
    
        width: 4vw;
    height: 4vw;
    margin-top: 4vw;
}
  


.content_login {
    display: block;
    background-image:"../assets/BG.png";
}
.B1 {
  width: 100%;
  text-align: -webkit-center;
  margin-top: 12.564102564102564VW;
}
   #Login{
    
      background:white;
     background-repeat: no-repeat;
     background-size: 101%;
     font-family: var(--font-titulo2);
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
   

   .logos_{
     display: flex;
   }

    .form_login h1{
      height: 4vw;
      color:white;
      font-weight: 500;
      font-size: 8.974358974358974VW;
      line-height: 2.2916666666666665VW;
      text-align: center;
      margin-bottom: 5.641025641025641VW !important;
      font-family: var(--Lato);
    
    }

   .form_login form{
     display: inline-grid;
   }

   

   .form_login  input{
     border-radius: 10vw;
     border: 0.052083333333333336VW solid #1E7E8B;
     width: 58.04871794871795VW;
     height: 12.86923076923077VW; 
     font-size: 3.3333333333333335VW;
     color: var(--color-4) !important;
     margin-bottom: 4.817948717948718VW !important;
    padding: 0vw 6vw;
      font-family: var(--Lato);
   }

   

   .form_login input:first-child{
     margin-bottom: 1.0416666666666665VW;
   }

  .form_login ::placeholder{
    color: #1E7E8B !important;
    font-size: 3.3333333333333335VW;
    font-weight: 600;
  }

   .form_login button{
     background:white;
     border: 0.052083333333333336VW solid #FA8433;
     height: 12.86923076923077VW;
     color: #FA8433;
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
 /* height: auto;
  float: right;
  margin-top: -12.5vw;
  z-index: 3;*/
}

.B0 {
  display: none;
}

.tl1{
  color:#1E7E8B;
  font-weight:bold;
  text-align:center;
  margin-top:10vw;

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
  .B0 img {
    width: 41.822916666666664VW;
    height: auto;
    margin-top: 6.8vw;
    margin-left: 19.2vw;
    z-index: 3;
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
    padding: 0vw 1vw;
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



}


</style>
