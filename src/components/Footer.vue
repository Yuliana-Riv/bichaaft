<template>
  <div class="bloquefooter">

    <!--modal carrito-->
    





    <div class="fila1footer">
      <div class="colmenu">
        <div class="menufooter">
          <h5>Menú</h5>
          <ul>
            <li><a href="/">Inicio</a></li>
            <li><a href="#nosotros">¿Quiénes somos?</a></li>
            <li><a href="#servicios">Servicios</a></li>
            <li><a href="#directorio">Directorio</a></li>
            <li><a href="#contacto">Contacto</a></li>
          </ul>
        </div>
        <img class="imgfoomv" src="../assets/imgfootermv.svg" />
        <img class="imgfoopc" src="../assets/imgfootermv.svg" />
      </div>
      <div class="infofooter">
        <h5>Información</h5>
        <div class="bloqueiff">
          <p class="titpif">Dirección</p>
          <p class="txtpif light">
            Hermosillo, Sonora
          </p><!---->
          <p class="txtpif ultpif light">San Carlos Nuevo Guaymas, Sonora</p> 

          <p class="titpif">Teléfono</p>
          <a href="tel:+5216221718298"
            ><p class="txtpif ultpif light">(622) 171 8298</p></a
          >

          <!--<p class="titpif">Horario</p>
          <p class="txtpif ultpif last light">Lun-Dom <br><span> –</span> 12 pm a 10 pm</p>--->
          <!--<p class="txtpif ultpif last">Domingo – 11:00 am a 6:00 pm</p>-->
        </div>
        <div class="redesfooter">
          <a
            href="https://www.facebook.com/BichaaMX"
            target="_blank"
            rel="noopener noreferrer"
            ><img src="../assets/custom/fb-i.svg" alt="Icono Facebook"
          /></a>
          <a
            class="btnigfo"
            href="https://www.instagram.com/bichaamx/"
            target="_blank"
            rel="noopener noreferrer"
            ><img src="../assets/custom/ig-i.svg" alt="Icono Instagram"
          /></a>
          <!--<a class="btnigfo" href="" target="_blank" rel="noopener noreferrer">
            <img src="../assets/custom/tt-i.svg" alt="Icono Tik Tok" />
          </a>-->
        </div>
      </div>
      <div class="newsfooter">
        <div class="fila1newsfo">
          <form @submit.prevent="suscribirse(email)">
            <h5 class="titnewslfo pc">
              Suscríbete a nuestro newsletter
            </h5>
            <h5 class="titnewslfo mo">
              Suscríbete a nuestro newsletter
            </h5>
            <div class="bloquenewsletter">
              <input
                type="email"
                name=""
                id=""
                placeholder="Correo electrónico"
                v-model="email"
              />
              <button type="submit" class="submitnewsl-btn">Enviar</button>
            </div>
            <div v-if="this.status == 'success'">
              <p class="cart_msg cart_success">{{ this.message }}</p>
            </div>
            <div v-if="this.status == 'error'">
              <p class="cart_msg cart_error">{{ this.message }}</p>
            </div>
          </form>
        </div>
        <div class="fila2newsfo">
          <div class="col1nefo">
            <a href="../views/Terms.vue"><p>Politicas de Privacidad</p></a>
            <a href="../views/Terms.vue"><p>Terminos de Uso</p></a>
          </div>
          <div class="col2nefo">
            <img src="../assets/imgfooter.svg" alt="" class="mo"/>
            <img src="../assets/logofooter.svg" alt="" class="pc"/>
          </div>
        </div>
      </div>
    </div>
    <div class="fila2footer">
      <p><span>Copyright 2022</span> © Todos los Derechos Reservados.</p>
    </div>
  </div>
</template>
<script>
import dayjs from "dayjs";
export default {
  data() {
    return {
      email: "",
      status: "",
      message: "",
    };
  },
  methods: {
    suscribirse: async function (email) {
      this.status = "";
      this.message = "";
      let sub_date = dayjs().format("YYYY-MM-DD");
      let data = {
        email,
        sub_date,
      };

      let result = await this.$store.dispatch("suscripciones/addItemSbs", {
        option: "suscripciones",
        item: data,
      });

      if (result.status == "error") {
        this.status = "error";
        this.message = result.message;
        console.log(this.message);
        this.delStatus();
      } else {
        // success
        this.status = "success";
        this.message = "Suscripción exitosa!";
        console.log(this.message);
        this.delStatus();
      }
    },
    delStatus: function () {
      setTimeout(() => this.delMsgs(), 3000);
    },
    delMsgs: function () {
      this.status = "";
      this.message = "";
    },
  },
};
</script>
<style scoped>
/* FOOOOTER */
.bloquefooter {
  background: var(--fs-bgfooter);
  padding-top: 13.285024154589372vw;
}

.fila1footer h5 {
  font-family: var(--font-titulo1);
  text-align: center!important;
  color: var(--co-titsecfo);
  font-size: var(--fs-titsecfomv);
  line-height: 7.367vw;
  font-weight: 600; 
}
.colmenu {
  text-align: center;
}
.colmenu ul {
  margin: 0;
  margin-block-start: 0 !important;
  margin-block-end: 0 !important;
  padding-inline-start: 0 !important;
}
.colmenu li {
  font-family: var(--font-parrafo2);
  font-size: var(--fs-txtmenufomv);
  color: var(--co-txtmenufo);
  text-align: center;
  list-style: none;
  line-height: 13.553140096618357vw;
  transition: .5s;
  font-weight: 500;
}
.colmenu li:hover { 
color: var(--font-foohover);
}
.bloqueiff a p,.col1nefo a p{
  transition: .5s;
}
.bloqueiff a p:hover,.col1nefo a p:hover{
color: var(--font-foohover);
} 
.imgfoopc {
  display: none;
}
.colmenu img {
  margin-top: 11.5vw;
  width: 40.097vw;
  height: auto;
  margin-bottom: 13.768115942028986vw;
}
.bloqueiff {
  text-align: center;
}
.bloqueiff p {
  font-family: var(--font-parrafo2);
  font-size: var(--fs-pinfofomv);
  margin: 0;
  line-height: 5.36231884057971vw;
  font-weight: 300;
}
.titpif {
  color: var(--co-titinfofo);
  font-weight: 400 !important;
}
.txtpif {
  color: var(--co-txtinfofo);
}
.ultpif {
  margin-bottom: 7.488vw !important;
}
.ultpif.last {
  margin-bottom: 9.179vw !important;
}
.redesfooter {
  text-align: center; 
}
.redesfooter img {
  width: 11.816vw;
  height: 11.816vw;
  filter: var(--sm-icon-color);
}
.btnigfo {
  margin-left: 5vw;
}
.infofooter {
  width: 86%;
  padding-bottom: 8.937vw;
  border-bottom: 1px solid white;
  margin: auto;
}
.newsfooter {
  width: 85%;
  margin: auto;
  padding-top: 11.83574879227053vw;
}
.fila1newsfo {
  padding-bottom: 18.357vw;
  border-bottom: 1px solid white;
}
.titnewslfo {
  font-family: var(--font-titulo2) !important; 
  text-align: center !important;
  margin: 0;
  margin-bottom: 8.696vw;
}
.bloquenewsletter {
    height: 20.807vw;
  display: flex;
  align-items: center;
  overflow: hidden;
}
.newsfooter input {
  width: 60%;
  font-size: 4.348vw;
    height: 20.107vw;
  background: transparent;
  border: 0.562vw solid #FA8433;
  border-right: 0;
  border-top-left-radius: 7.246376811594203vw;
  border-bottom-left-radius: 7.246376811594203vw;
  border-top-right-radius: 0;
  border-bottom-right-radius: 0;
  text-indent: 6%;
  color: #ffffff !important;
  font-family: var(--font-parrafo2);
  font-weight: 300;
  padding: 0;
  -webkit-appearance: none;
}
.newsfooter input::placeholder {
  color: #ffffff;
  opacity: 0.75;
  font-family: var(--font-titulo2);
  font-weight: 300;
  font-style: italic;
}
.newsfooter button {
  background:#FA8433;
  font-family: var(--font-titulo2);
  font-weight: 700;
    height: 20.807vw;
  border: 0.362vw solid #FA8433;
  width: 40%;
  font-size: 4.348vw;
  color: #ffffff;
  cursor: pointer;
  transition: 0.5s;
  border-top-right-radius: 7.246376811594203vw;
  border-bottom-right-radius: 7.246376811594203vw;
  padding: 0;
}
.newsfooter button:hover {
  background:#F7E3DB;
  color: #FA8433;  
  border: 0.0562vw solid #F7E3DB;
  } 
.fila2newsfo {
  display: flex;
  flex-direction: column-reverse;
}
.col2nefo {
  text-align: center;
  padding-top: 8.937198067632849vw;
  padding-bottom: 10.145vw;
}
.col2nefo img {
  width: 48.841vw;
  height: auto;
  margin: auto;
}
.col2nefo img.mo{
  display: flex;
}
.col2nefo img.pc{
  display: none;
}
.col1nefo {
  text-align: center;
  display: block;
}
.col1nefo a {
  width: 100%;
  color: var(--co-titinfofo);
  font-family: var(--font-parrafo2);
  font-size: var(--fs-pinfofomv);
}
.col1nefo a p {
  margin: 0;
  margin-top: 3.5816425120772946vw;
}
.fila2footer {
  margin: auto;
  width: 85%;
  padding-bottom: 19.565vw;
}
.fila2footer p {
  color: var(--co-txtcopy);
  font-family: var(--font-titulo2);
  font-size: var(--fs-txtcopymv);
  text-align: center;
  margin: 0;
  margin-top: 6.763vw;
}
.cart_msg {
  position: relative;
  top: 2vw;
}
 .txtpif.light {
    font-weight: 400!important;
    font-family: var(--font-parrafo2);
}
@media (max-width: 1024px) {
  .menufooter h5 {
    display: block;
    margin-top: 0;
    margin-bottom: 3.971vw;
  }
  .infofooter h5 {
    text-align: center!important;
    font-size: 5.314vw;
    margin: 0 0 5.797vw;
    font-family: 'Inter';
  }
  .bloqueiff {
    text-align: center;
    width: 59.179vw;
    margin: auto;
}
 .txtpif span{
  display: none;
 }
 .txtpif br{
  display: block;
 }
.titnewslfo.mo {
  display: block;
    width: 100%; 
}
.titnewslfo.pc {
  display: none;
}
}
@media (min-width: 1024px) {
.titnewslfo {
  font-family: var(--font-titulo1) !important;
  }
.titnewslfo.mo {
  display: none;
}
.titnewslfo.pc {
  display: block;
  text-align: left!important;
}
.col2nefo img.mo{
  display: none;
}
.col2nefo img.pc{
  display: flex;
}
 .txtpif span{
  display: inline;
 }
 .txtpif br{
  display: none;
 } 
  .col2nefo {
    padding-bottom: 0;
  }
  .titpif {
    color: var(--co-titinfofo);
    font-weight: 600 !important;
  }
  .bloquefooter {
    padding-top: 3.802083333333333vw;
  }
  .fila1footer {
    display: flex;
    width: 85%;
    border-bottom: 0px solid #55cd00;
    margin: auto;
    padding-left: 8.854166666666668vw;
    height: 20.260416666666668vw;
  }
  .colmenu {
    width: 27%;
    display: flex;
    border-right: 1px solid #ffffff;
    padding-top: 0.8854166666666666vw;
  }
  .menufooter h5 {
    margin-bottom: 1.7187500000000002vw !important;
  }
  .infofooter {

    width: 13.49vw;
    border-right: 1px solid #ffffff;
    margin: 0;
    padding-left: 4.270833333333333vw;
    padding-right: 3.125vw;
    padding-top: 0.8854166666666666vw;
    padding-bottom: 0vw;
    border-bottom: 0px solid #55cd00;
}
  .newsfooter {
    width: 40%;
    padding-top: 0.8854166666666666vw;
    margin: 0 !important;
    padding-left: 4.270833333333333vw;
  }
  .fila1footer h5 {
    text-align: left !important;
    font-size: 0.938vw;
    line-height: 1vw;
    font-weight: 700;
    margin: 0;
  }
  .colmenu li {
    font-size: var(--fs-txtmenufo);
    text-align: left;
    list-style: circle !important;
    line-height: 2.0458333333333334vw;
    margin-left: 1.25vw;
    font-weight: 400;
}
  .imgfoomv {
    display: none;
  }
  .imgfoopc {
    display: block;
  }
  .colmenu img {
    margin-top: 0;
    width: 10.104vw;
    height: 13.594vw; 
    margin-bottom: 11.353vw;
    margin-left: 2.708vw;
  }
  .bloqueiff p {
    font-size: var(--fs-txtinfofo);
    margin: 0;
    line-height: 1.1250000000000002vw;
    text-align: left;
    font-family: var(--font-parrafo2);
  }
  .ultpif {
    margin-bottom: 1.3541666666666667vw !important;
    /*display: flex;*/
  }
  .ultpif.last {
    margin-bottom: 0 !important;
  }
  .redesfooter {
    /*padding-top: 1.34375vw; 
    display: none;*/
    width: fit-content;
  }
  .redesfooter img {
    width: 1.875vw;
    height: 1.875vw;
  }
  .btnigfo {
    margin-left: 1vw;
  }
  .infofooter h5 {
    margin-bottom: 1.25vw !important;
  }
  .titnewslfo {
    /*font-family: var(--font-titulo2) !important;*/
    font-weight: 800;
    margin-bottom: 1.0416666666666665vw !important;
  }
  .bloquenewsletter {
    /*height: 2.604166666666667vw;*/
    height: 2.8804166666666666vw;
    display: flex;
    align-items: center;
  }
  .newsfooter input {
    width: 54%;
    height: 2.166666666667vw;
    border-top-left-radius: 7.246376811594203vw;
    border-bottom-left-radius: 7.246376811594203vw;
    text-indent: 8%;
    color: #ffffff !important;
    font-size: 0.729vw;
    border: 0.162vw solid #FA8433;
    border-right: none;
  }
.newsfooter input::placeholder {
  color: #ffffff;
  opacity:1;  
  font-style: normal;
}
  .newsfooter button {
    height: 2.5vw;
    width: 15%;
    font-size: 0.938vw;
    color: #ffffff;
    border-top-right-radius: 7.246376811594203vw;
    border: 0.162vw solid #FA8433;
    border-bottom-right-radius: 7.246376811594203vw;
  }
  .fila1newsfo {
    padding-bottom: 0vw;
    border-bottom: 0px solid #55cd00;
  }
  .fila2newsfo {
    display: flex;
    flex-direction: row;
    /*padding-top: 9.5vw;*/
    padding-top: 10.15vw;
    width: 73%;
  }
  .col1nefo {
    width: 50%;
  }
  .col2nefo {
    width: 50%;
    padding-top: 0vw;
  }
  .col1nefo a {
    width: 30%;
    font-size: var(--fs-txtinfofo);
    text-align: left;
  }
  .col1nefo a p {
    margin: 0;
    margin-top: 0.3125vw;
    font-weight: 300;
  }
  .col2nefo img { 
    width: 10.573vw;
    height: auto;
    margin-top: -0.5vw;
}
  .fila2footer {
    padding-bottom: 2.3958333333333335vw;
    border-top: 1px solid #ffffff;
    margin-top: 2vw;
    width: 92%;
  }
  .fila2footer p {
    font-size: var(--fs-txtcopy);
    text-align: center;
    margin: 0;
    margin-top: 1.5625vw;
    width: 92%;
  }
}
</style>