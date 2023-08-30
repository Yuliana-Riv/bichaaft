<template >
  <div id="Home" class="homepage">
    <!-- Header aqui -->
    <FixedItems />
    <Navigator />
    <div class="modal-container" :class="{ nonemodal: mdcar == false }">
      <ModalCar
        @close="mdcar = false"
        :class="{ transitionL: mdcar == true }"
      />
    </div>
    <div class="section1">
      <div class="slidemain">
        <section v-if="banner.length == 1">
          <a :href="banner[0].link">
            <img
              class="slidemv"
              :src="
                url +
                '/' +
                endpointCodes.get +
                '/get-banner-image/' +
                banner[0].image_mv
              "
              alt="" />
            <img
              class="slidepc"
              :src="
                url + '/' + endpointCodes.get + '/get-banner-image/' + banner[0].image
              "
              alt=""
          />
          </a>

        </section>
        <carousel
          :perPage="1"
          :navigationEnabled="false"
          :paginationEnabled="false"
          v-else
        >
          <slide v-for="(s, i) in banner" :key="i">
            <a :href="s.link">
            <img
              class="slidemv"
              :src="
                url +
                '/' +
                endpointCodes.get +
                '/get-banner-image/' +
                s.image_mv
              "
              alt="" />
            <img
              class="slidepc"
              :src="
                url + '/' + endpointCodes.get + '/get-banner-image/' + s.image
              "
              alt="" />
            </a>
          </slide>
        </carousel>
      </div>
      <div id="nosotros" class="filanosotros">
        <!-- Indicador seccion -->
        <div class="idsecc">
          <h5>01.</h5>
          <div class="hr"></div>
          <h5>NOSOTROS</h5>
        </div>
        <!-- Bloque Quienes somos -->
        <div class="bloqueqs">
          <div class="col1-qs">
            <!--   <img src="../assets/btnvideo.svg" alt="btn" class="btnvi" />
            <img class="imgqs1pc" src="../assets/imgqspc.jpg" alt="" /> -->
          </div>
          <div class="col2-qs">
            <h2>¿Quiénes Somos?</h2>
            <p class="orp mb2">
              Somos una empresa dedicada al servicio de transporte privado en la
              ciudad de San Carlos, Sonora, enfocados en brindarte excelente
              trato y un rápido nivel de respuesta a la hora de reservar. Bichaá
              también cuenta con paquetes ideales para tus eventos y paseos
              turísticos.
            </p>
            <section>
              <p class="orp w50qs tl">Misión</p>
              <p class="mb2 w50qs fs3">
                Ofrecer un buen servicio de transporte turístico para que el
                usuario viva una grata experiencia y llegue satisfecho a su
                destino.
              </p>
            </section>
            <section>
              <p class="orp w50qs tl">Visión</p>
              <p class="mb2 w50qs fs3">
                Ser la mejor empresa de transportes turísticos en San Carlos,
                reconocida por la calidad y servicio que brindamos.
              </p>
            </section>
            <img src="../assets/nos1.svg" alt="nos" class="nos1 mo" />
            <img src="../assets/nos1pc.svg" alt="nos" class="nos1 pc" />
            <section class="mt3">
              <p class="orp w50qs tl">Valores</p>
              <p class="mb2 w50qs fs3">
                Honestidad <br />
                Responsabilidad <br />
                Calidad <br />
                Puntualidad
              </p>
            </section>
            <!----<div class="videoc"> 
              <img class="imgqs1mv" src="../assets/imgqsmv.png" alt="" />
            </div>-->
          </div>
        </div>
      </div>
    </div>

    <div
      id="servicios"
      class="sectionservicios" 
    >
      <!-- Indicador seccion -->
      <div class="idsecc">
        <h5>02.</h5>
          <div class="hr"></div>
        <h5>Servicios</h5>
      </div>
      <h2 class="titservicios">Servicios</h2>
      <div class="servs-c">
        <div class="serv-item">
          <img src="../assets/serv1.png" alt="serv" />
          <p class="tl">Bichaá-tuk</p>
          <p class="stl">
            Disfruta de la experiencia turística en nuestros Tuk Tuk dentro de
            la ciudad de San Carlos.
          </p>
          <a href="https://wa.link/gmgcuf" class="btn">
            <div>Reservar por Whatsapp</div>
          </a>
        </div>
        <div class="serv-item">
          <img src="../assets/serv2.png" alt="serv" />
          <p class="tl">Van</p>
          <p class="stl">
            Servicio de transporte seguro y confiable; de Hermosillo a San
            Carlos, y viceversa.
          </p>
          <a href="" class="btn prox">
            <div>¡Próximamente!</div>
          </a>
        </div>
      </div>
    </div>
    <div class="bloquepromo">
      <a class="contpc"
        ><img class="imgpromopc" src="../assets/promopc.png" alt=""
      /></a>
      <a class="contmo"
        ><img class="imgpromomv" src="../assets/promomv.jpg" alt=""
      /></a>
    </div>
    <!--<div class="sectionbanner2">
      <img class="imgban2mv" src="../assets/banner2mv.png" alt="" />
      <img class="imgban2pc" src="../assets/banner2pc.png" alt="" />
    </div> -->

    <!--DIRECTORIO-->
    <div
      id="directorio"
      class="sectionservicios" 
    >
      <!-- Indicador seccion -->
      <div class="idsecc">
        <h5>03.</h5>
          <div class="hr"></div>
        <h5>Directorio</h5>
      </div>
      <h2 class="titservicios">Conoce a nuestros chóferes</h2>
      <p class="subservicios">
        Todos nuestros choferes están capacitados para dar la mejor calidad en
        servicio y brindarte <br> ¡Conoce a cada uno de ellos!
      </p>
      <div class="servs-c dir-c">
        <section class="cdflx">
          <div class="serv-item">
            <img src="../assets/misael.png" alt="serv" />
            <p class="tl">Misael</p>
            <p class="stl tl2">
            </p>
            <p class="stl">Mi nombre es Misael, soy originario de Guaymas. Actualmente 
              curso la Licenciatura de Psicología. Mi experiencia laboral está conformada 
              por una excelente atención al cliente, conocimientos de RCP, qué hacer en 
              casos de catástrofes y reconocimientos de áreas turísticas. 

            </p>
          </div> 
          
          <div class="serv-item">
            <img src="../assets/karel.png" alt="serv" />
            <p class="tl">Karel</p>
            <p class="stl tl2">
            </p>
            <p class="stl">Me llamo Karel, soy originario de Guaymas. Estudié por 
              2 años ingeniería pero actualmente estoy en la Licenciatura de Derecho.
              Me gusta la mecánica de carros y practicar deportes de contacto, planeo 
              algún día tener un buen negocio.
            </p>
          </div> 
        </section>

        <a href="https://wa.link/012603" class="btn" target="_blank" rel="noopener noreferrer">
          <div>Únete a Bichaá</div>
        </a>
      </div>
    </div>
    <!---SUCURSALES--->
    <!--    <div
      class="sectionsucursales"
      id="sucursales"
      v-if="suc == 'No se encontraron coincidencias.'"
    ></div>
    <div v-else>
      <div class="sectionsucursales" id="sucursales" v-if="suc.length > 1">
        <div class="idsecc">
          <h5>03.</h5>
          <hr />
          <h5>Ubicaciones</h5>
        </div>
        <div class="bloquesucursales">
          <h2>Sucursales</h2>
          <div class="bloquebtnubi">
            <a @click="showModalCarretas = !showModalCarretas" class="btnubi"
              ><p>Ubica tu Aquimis más cercano</p></a
            >
          </div>
          <div v-if="showModalCarretas" class="modal_view_cnt">
            <div id="modal_ubicaciones">
              <p @click="showModalCarretas = false" class="close_modal_btn">
                &#10006;
              </p>
              <div class="modal_iframe">
                <iframe
                  src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3486.28556924302!2d-110.94375718416906!3d29.09724946964509!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x86ce85109e7793b3%3A0x2c75980f3fd06ea6!2sLa%20Carreta%20Verde%20Kino!5e0!3m2!1ses!2smx!4v1669134602141!5m2!1ses!2smx"
                  width="600"
                  height="450"
                  style="border: 0"
                  allowfullscreen=""
                  loading="lazy"
                  referrerpolicy="no-referrer-when-downgrade"
                ></iframe>
              </div>
            </div>
          </div>

          <div class="F7">
            <div class="Mobil">
              <carousel
                v-if="suc.length > 3"
                :per-page="1"
                :mouse-drag="true"
                :navigation-enabled="true"
                :navigationNextLabel="sright"
                :navigationPrevLabel="sleft"
                :loop="true"
                :paginationEnabled="false"
              >
                <slide v-for="(item, key) in sucursales2" :key="key">
                  <div
                    class="F7Content"
                    v-for="(item2, key2) in item"
                    :key="key2"
                  >
                    <img
                      class="F7I1"
                      v-if="item2.image !== ''"
                      :src="
                        url +
                        '/' +
                        endpointCodes.get +
                        '/sucursal-img/' +
                        item2.image
                      "
                    />
                    <p class="F7T1">{{ item2.name }}</p>
                    <p class="F7T F7T2">{{ item2.address }}</p>

                    <p class="F7T">Lun a Sab 7:00 am a 3:00 pm</p>
                    <a
                      :href="item2.wlink"
                      target="_blank"
                      ref="noopener noreferrer"
                    >
                      <div class="F7F3">
                        <img src="../assets/Whatsapp2.png" />
                        <p>{{ item2.phone }}</p>
                      </div>
                    </a>
                  </div>
                </slide>
              </carousel>
              <div v-else>
                <div v-for="(item, key) in sucursales2" :key="key">
                  <div class="F7Content">
                    <img
                      class="F7I1"
                      v-if="item.image !== ''"
                      :src="
                        url +
                        '/' +
                        endpointCodes.get +
                        '/sucursal-img/' +
                        item.image
                      "
                    />
                    <p class="F7T1">{{ item.name }}</p>
                    <p class="F7T F7T2">{{ item.address }}</p>

                    <p class="F7T">Lun a Sab 7:00 am a 3:00 pm</p>
                    <a
                      :href="item.wlink"
                      target="_blank"
                      ref="noopener noreferrer"
                    >
                      <div class="F7F3">
                        <img src="../assets/Whatsapp2.png" />
                        <p>{{ item.phone }}</p>
                      </div>
                    </a>
                  </div>
                </div>
              </div>
            </div>
            <div class="Desktop" v-if="sucursales"> 
              <carousel
                v-if="suc.length > 6"
                :per-page="1"
                :mouse-drag="true"
                :navigation-enabled="true"
                :navigationNextLabel="sright"
                :navigationPrevLabel="sleft"
                :loop="true"
                :paginationEnabled="false"
              >
                <slide v-for="(item, key) in sucursales" :key="key">
                  <div
                    class="F7Content"
                    v-for="(item2, key2) in item"
                    :key="key2"
                  >
                    <img
                      class="F7I1"
                      v-if="item2.image !== ''"
                      :src="
                        url +
                        '/' +
                        endpointCodes.get +
                        '/sucursal-img/' +
                        item2.image
                      "
                    />
                    <img
                      class="F7I1"
                      v-else-if="item2.image == ''"
                      src="../assets/Sucursal_Img.png"
                    />
                    <p class="F7T1">{{ item2.name }}</p>
                    <p class="F7T F7T2">{{ item2.address }}</p>

                    <p class="F7T">Lun a Sab 7:00 am a 3:00 pm</p>
                    <a
                      :href="item2.wlink"
                      target="_blank"
                      ref="noopener noreferrer"
                    >
                      <div class="F7F3">
                        <img src="../assets/Whatsapp2.png" />
                        <p>{{ item2.phone }}</p>
                      </div>
                    </a>
                  </div>
                </slide>
              </carousel>
              <carousel
                v-else
                :per-page="6"
                :mouse-drag="true"
                :navigation-enabled="true"
                :navigationNextLabel="sright"
                :navigationPrevLabel="sleft"
                :loop="true"
                :paginationEnabled="false"
              >
                <slide v-for="(item, key) in sucursales" :key="key">
                  <div class="F7Content">
                    <img
                      class="F7I1"
                      v-if="item.image !== ''"
                      :src="
                        url +
                        '/' +
                        endpointCodes.get +
                        '/sucursal-img/' +
                        item.image
                      "
                    />
                    <img
                      class="F7I1"
                      v-else-if="item.image == ''"
                      src="../assets/Sucursal_Img.png"
                    />
                    <p class="F7T1">{{ item.name }}</p>
                    <p class="F7T F7T2">{{ item.address }}</p>

                    <p class="F7T">Lun a Sab 7:00 am a 3:00 pm</p>
                    <a
                      :href="item.wlink"
                      target="_blank"
                      ref="noopener noreferrer"
                    >
                      <div class="F7F3">
                        <img src="../assets/Whatsapp2.png" />
                        <p>{{ item.phone }}</p>
                      </div>
                    </a>
                  </div>
                </slide>
              </carousel>
            </div>
          </div>
        </div>
      </div>
      <div
        class="sectionsucursales"
        id="sucursales"
        v-else-if="suc.length == 1"
      >
        <div class="idsecc">
          <h5>03.</h5>
          <hr />
          <h5>CONTACTO</h5>
        </div>
        <div class="matriz-cont">
          <p class="tl">Contáctanos</p>
          <p class="subtl">
            Disfruta del dulce sabor de las mejores Coyotas de Sonora. <br />
            Haz tus compras en línea para recibir a domicilio, manda un mail con
            tus comentarios o visita nuestra sucursal. Nos encantará saber tu
            opinión y responder todas tus dudas.
          </p>
          <div class="threeitems">
            <div class="item one">
              <img src="../assets/icon1.svg" alt="phone" />
              <a href="tel:+526622105647">Tel. {{ suc[0].phone }}</a>
            </div>
            <div class="item two">
              <img src="../assets/icon2.svg" alt="address" />
              <p>{{ suc[0].address }}</p>
            </div>
            <div class="item three">
              <img src="../assets/icon3.svg" alt="mail" />
              <a href="mailto:lourdescoyotas@gmail.com"
                >lourdescoyotas@gmail.com</a
              >
            </div>
          </div>
        </div>
        <iframe
          class="mapcont"
          src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d871.61928273528!2d-110.94909978097267!3d29.091592051043943!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x86ce85cb694afce7%3A0xb04478af9593e80!2sCoyotas%20Lourdes!5e0!3m2!1sen!2smx!4v1670365999345!5m2!1sen!2smx"
          width="600"
          height="450"
          style="border: 0"
          allowfullscreen=""
          loading="lazy"
          referrerpolicy="no-referrer-when-downgrade"
        ></iframe>
      </div>
    </div>--->

    <!---REDES SOCIALES--->
    <div id="siguenos" class="sectionredes">
      <div class="idsecc">
        <h5>04.</h5>
          <div class="hr"></div>
        <h5>Redes sociales</h5>
      </div>
      <div class="bloqueredes">
        <h2>Ùnete a nuestra comunidad</h2>
        <p class="txtredes">
          Se parte de la comunidad de Bichaá, síguenos en redes sociales y sé el primero en enterarte de las novedades.
        </p>
        <div class="fila-br">
          <div class="fbr img1br">
            <img src="../assets/imagebr1.png" alt="" />
          </div>
          <div class="fbr img2br">
            <img src="../assets/imagebr2.png" alt="" />
          </div>
          <div class="fbr img1br img3br">
            <img src="../assets/imagebr3.png" alt="" />
          </div>
          <div class="fbr img2br img4br">
            <img src="../assets/imagebr4.png" alt="" />
          </div>
        </div>
        <div class="bloquebtnig">
          <a
            href="https://www.instagram.com/bichaamx/"
            target="_blank"
            rel="noopener noreferrer"
          >
            <div class="btnig">
              <h5>@bichaamx</h5>
            </div>
          </a>
        </div>
      </div>
    </div>
    <!---    <div class="sectiontiktok">
      <div class="idsecc">
        <h5 class="cotik">05.</h5>
        <hr />
        <h5 class="cotik">Tik Tok</h5>
      </div>
      <div class="bloquetiktok">
        <section>
          <h2>Encuéntranos en</h2>
          <img class="imgtiktok" src="../assets/tiktokpc.png" />
        </section>
        <section>
          <h6>Únete a nuestra comunidad y disfruta de recetas exclusivas.</h6>
          <div class="bloquebtntik">
            <a class="btntik" href="https://www.tiktok.com/@aquimis_huevos"
              ><p>Coyotas Lourdes</p></a
            >
          </div>
        </section>
      </div>
    </div>
    -->
    <div class="sectionbanner8">
      <img class="imgban2mv" src="../assets/banner8mv.png" alt="" />
      <img class="imgban2pc" src="../assets/banner8pc.png" alt="" />
    </div>
    <div class="sectioncontacto" id="contacto">
      <!--<div class="idsecc">
        <h5>05.</h5>
        <hr />
        <h5>Contacto</h5>
      </div>--->
      <div class="flexic">
        <form @submit.prevent="enviarMail(name, phone, email, mensaje)">
          <div class="sectionformulario">
            <h2 class="titform mo">¿Dudas o sugerencias?</h2>
            <h2 class="titform pc">¿Dudas o sugerencias?</h2>
            <p class="txt-ctc">
              Te invitamos a dejar tu mensaje, nos pondremos en contacto contigo
              lo antes posible, ¡gracias!
            </p>
            <div class="bloqueform">
              <input
                class="inputbf inputname"
                type="text"
                placeholder="Nombre"
                v-model="name"
              />
              <input
                class="inputbf inputnumber"
                type="number"
                placeholder="Celular"
                v-model="phone"
              />
              <input
                class="inputbf inputemail"
                type="email"
                placeholder="Correo"
                v-model="email"
              />
              <!--<input
                class="inputbf inputsucursal"
                type="sucursal"
                placeholder="Sucursal"
                v-model="sucursal"
              />-->
              <textarea
                class="texa"
                cols="30"
                rows="10"
                placeholder="Mensaje"
                v-model="mensaje"
              ></textarea>
              <div class="ad-btn">
                <div class="bloqueaviso"> 
                  <div class="inpcheck" @click="aviso == true ? aviso = false : aviso = true">
                    <div class="checked" v-if="aviso == true"></div>
                  </div>
                  <p class="txtaviso">
                    He leído el <a href="#">Aviso de Privacidad</a> antes de
                    enviar el formulario.
                  </p>
                </div>
                <button type="submit" class="btnform">
                  <p class="txtbtn">Enviar</p>
                </button>
              </div>

              <div v-if="this.status == 'success'">
                <p class="cart_msg cart_success">{{ this.msg }}</p>
              </div>
              <div v-if="this.status == 'error'">
                <p class="cart_msg cart_error">{{ this.msg }}</p>
              </div>
            </div>
          </div>
        </form>
        <img src="../assets/carreta1.png" alt="" class="formimg mo" />
        <img src="../assets/carreta1pc.png" alt="" class="formimg pc" />
      </div>
    </div>
    <Footer />
  </div>
</template>
<script>
import { mapActions } from "vuex";
import Navigator from "../components/Navigator";
import Footer from "../components/Footer";
import FixedItems from "../components/FixedItems";
import ModalCar from "./carrito/modalCar";
import { Carousel, Slide } from "vue-carousel";
import { url, endpointCodes } from "../global/index";

export default {
  name: "Home",
  components: {
    Carousel,
    Slide,
    Navigator,
    Footer,
    FixedItems,
    ModalCar,
  },
  data() {
    return {
      mdcar: false,

      url: url,
      endpointCodes,
      showModalCarretas: false,
      catsel: "",
      scsel: "Nutritivos",

      nextA: '<div class="divPrev0"><p class="NButton">&#9664;</p></div>',
      nextB: '<div class="divPrev0"><p class="NButton">&#9654;</p></div>',
      sleft: '<img src="' + require("../assets/sleft.svg") + '"/>',
      sright: '<img src="' + require("../assets/sright.svg") + '"/>',



      hide: false,
      aviso: false,
      name: "",
      phone: "",
      email: "",
      sucursal: "",
      mensaje: "",
      status: "",
      msg: "",

      currentA: [],
      currentA2: [],
      titulo: "",
      subtitulo: "",

      cartsel: 0,


      conductorA: [
        {name:''},
        {name:''},
        {name:''}
      ],

      status: "",
      message: "",
      cart: localStorage.getItem("cart"),
    };
  },
  metaInfo() {
    return {
      title: "Bienvenidos",
      titleTemplate: "%s | Bichaá",
      htmlAttrs: {
        lang: "es",
      },
      meta: [
        { charset: "utf-8" },
        {
          name: "description",
          content: "Bichaá.",
        },
        { name: "viewport", content: "width=device-width, initial-scale=1" },
      ],
    };
  },
  async created() {
    await this.getAllInfoBnr("banner");
    await this.getAllInfoCtg("category");
    await this.getAllInfoPrd("product");
    await this.getAllInfoScl("sucursal");
    /*this.currentA2 = this.items[0];
    this.currentA = this.items[this.number];
    this.catsel = this.categories[0].name;*/
  },
  computed: {
    slideC(side) {
      if (side == "l") {
      }
      if (side == "r") {
      }
    },
    number: {
      cache: false,
      get() {
        return this.$refs.itemsS ? this.$refs.itemsS.currentPage : 0;
      },
    },
    datass() {
      return this.categories[this.$refs.itemsS.currentPage];
    },
    banner() {
      return this.$store.getters["banner/data"];
    },
    products() {
      //return this.$store.getters["product/data"];
      let pro = this.$store.getters["product/data"];
      let cats = this.catsel;
      let ar1 = [];
      let arr = [];
      if (Array.isArray(pro)) {
        for (let i = 0; i < pro.length; i++) {
          if (pro[i].category_name == cats) {
            ar1.push(pro[i]);
          }
        }
        for (let i = 0; i < ar1.length; i++) {
          if (ar1[i].stock !== "Sin stock") {
            arr.push(ar1[i]);
          }
        }
        let namec = [...new Set(arr.map(({ name }) => name))]
          .map((t) =>
            Object.assign({ [t]: arr.filter(({ name }) => name === t).length })
          )
          .reduce((acc, v) => Object.assign(acc, v), {});

        let res = Object.keys(namec).reduce(
          (acc, t) =>
            namec[t] === 1
              ? acc.concat(
                  Object.assign({
                    name_pro: t,
                    descr_pro: arr.filter(({ name }) => name === t)[0].descr,
                    img_pro: arr.filter(({ name }) => name === t)[0].image,
                    results: arr.filter(({ name }) => name === t),
                  })
                )
              : acc.concat(
                  Object.assign({
                    name_pro: t,
                    descr_pro: arr.filter(({ name }) => name === t)[0].descr,
                    img_pro: arr.filter(({ name }) => name === t)[0].image,
                    results: arr.filter(({ name }) => name === t),
                  })
                ),
          []
        );
        return res;
      } else {
        return "No se encontraron coincidencias.";
      }
    },
    productsmo() {
      let pro = this.$store.getters["product/data"];
      let cats = this.datass.name;
      let dai = 0;
      let ar1 = [];
      let arr = [];
      if (Array.isArray(pro)) {
        for (let j = 0; j < pro.length; j++) {
          if (pro[j].category_name == cats) {
            ar1.push(pro[j]);
          }
        }
        for (let i = 0; i < ar1.length; i++) {
          if (ar1[i].stock !== "Sin stock") {
            arr.push(ar1[i]);
          }
        }
        let namec = [...new Set(arr.map(({ name }) => name))]
          .map((t) =>
            Object.assign({ [t]: arr.filter(({ name }) => name === t).length })
          )
          .reduce((acc, v) => Object.assign(acc, v), {});

        let res = Object.keys(namec).reduce(
          (acc, t) =>
            namec[t] === 1
              ? acc.concat(
                  Object.assign({
                    name_pro: t,
                    descr_pro: arr.filter(({ name }) => name === t)[0].descr,
                    img_pro: arr.filter(({ name }) => name === t)[0].image,
                    results: arr.filter(({ name }) => name === t),
                  })
                )
              : acc.concat(
                  Object.assign({
                    name_pro: t,
                    descr_pro: arr.filter(({ name }) => name === t)[0].descr,
                    img_pro: arr.filter(({ name }) => name === t)[0].image,
                    results: arr.filter(({ name }) => name === t),
                  })
                ),
          []
        );
        return res;
      } else {
        return "No se encontraron coincidencias.";
      }
    },
    categories() {
      return this.$store.getters["category/data"];
    },
    suc() {
      return this.$store.getters["sucursal/data"];
    },
    sucursales() {
      let arr = this.$store.getters["sucursal/data"];
      if (arr !== "No se encontraron coincidencias.") {
        let narr = [];
        if (arr.length > 6) {
          for (let i = 0; i < arr.length; i += 6) {
            let add = arr.slice(i, i + 6);
            narr.push(add);
          }
          console.log(arr);
          return narr;
        } else {
          return arr;
        }
      } else {
        return "No se encontraron coincidencias.";
      }
    },
    sucursales2() {
      let arr = this.$store.getters["sucursal/data"];
      let narr = [];
      if (arr !== "No se encontraron coincidencias.") {
        if (arr.length > 3) {
          for (let i = 0; i < arr.length; i += 3) {
            let add = arr.slice(i, i + 3);
            narr.push(add);
          }
          return narr;
        } else {
          return arr;
        }
      } else {
        return "No se encontraron coincidencias.";
      }
    },
  },
  methods: {
    ...mapActions("banner", ["getAllInfoBnr"]),
    ...mapActions("category", ["getAllInfoCtg"]),
    ...mapActions("product", ["getAllInfoPrd"]),
    ...mapActions("sucursal", ["getAllInfoScl"]),

    ...mapActions("carrito", ["getCart"]),
    ...mapActions("carrito", ["getCartCopy"]),

    //***CART METHODS */

    async obtenerCarritos() {
      await this.getCart();
      await this.getCartCopy();
    },
    agregarItem: async function (cantidad, arrsele) {
      let payload = {
        item: arrsele,
        _ctk: localStorage.getItem("_ctk"),
        cantidad,
      };

      let result = await this.$store.dispatch("carrito/editItemCrt", {
        option: "add_item",
        item: payload,
      });

      if (result.status == "error") {
        this.status = "error";
        this.message = result.message;
        this.delStatus();
      } else {
        // success
        await this.obtenerCarritos();
        this.mdcar = true;
        this.$router.push("/modalcart").catch((err) => {});
      }
    },

    /**END CART METHODS */

    catselect(val) {
      let array = this.items;
      this.catsel = val;
      let arr = [];
      for (let i = 0; i < array.length; i++) {
        if (array[i].categoria == val) {
          arr.push(array[i]);
        }
      }
      this.currentA2 = arr[0];
      this.scsel = arr[0].subcategoria;
    },
    subselect(val1, val2, val3) {
      let array = this.items;
      this.scsel = val2;
      let arr = [];
      for (let i = 0; i < array.length; i++) {
        if (array[i].categoria == val1) {
          arr.push(array[i]);
        }
      }

      this.currentA2 = arr[val3];
    },

    NArrays(array, number) {
      console.log("3 " + array.length);
      if (this.itemsorted.length < array.length) {
        number += 2;
        this.itemsorted = array.slice(0, number);
        console.log("2 " + number);
      }
      if (number >= array.length) {
        this.hide = true;
      }
    },

    delStatus: function () {
      setTimeout(() => this.delMsgs(), 5000);
      /*this.close(), 3000);*/
    },
    delMsgs: function () {
      this.status = "";
      this.msg = "";
    },
    enviarMail: async function (name, phone, email, mensaje) {
      this.msg = "";
      this.status = "";

      if (this.aviso == false) {
        this.msg = "Acepta los términos y condiciones.";
        this.status = "error";
      } else if (name == undefined || name == "" || name == null) {
        this.msg = "El campo nombre no es valido.";
        this.status = "error";
      } else if (phone == undefined || phone == "" || phone == null) {
        this.msg = "El campo medio no es valido.";
        this.status = "error";
      } else if (email == undefined || email == "" || email == null) {
        this.msg = "El campo correo no es valido.";
        this.status = "error";
      } else if (mensaje == undefined || mensaje == "" || mensaje == null) {
        this.msg = "El campo comentarios no es valido.";
        this.status = "error";
      } else {
        let data = {
          name: name,
          phone: phone,
          email: email,
          mensaje: mensaje,
        };
        let response = await this.$store.dispatch(
          "admin/enviarMailContacto",
          data
        );
        console.log(response);
        if (response.status == "success") {
          this.status = "success";
          this.msg = "Mensaje enviado con exito.";
          this.name = "";
          (this.phone = ""), (this.email = ""), (this.mensaje = "");
          this.delStatus();
        } else {
          this.status = "error";
          this.msg =
            "Lo sentimos ha ocurrido un error al intentar entregar tu mensaje.";
        }
      }
    },
    /*adjustHeight() {
      let d = document.getElementsByClassName("slide-item")[0];
      console.log(d.offsetHeight);
      let s = document.getElementsByClassName("slideservicios")[0];
      s.style.height = d.offsetHeight;
    },**/
  },
  mounted() {
   /* window.addEventListener("load", this.adjustHeight);
    this.itemsorted = this.items.slice(0, 2);*/
  },
};
</script>
<style scoped>
.purple {
  color: #8c3aaa !important;
}
.rose {
  color: #d376b9 !important;
}
.purplet {
  background: #8c3aaa !important;
}
.roset {
  background: #d376b9 !important;
}
.pc {
  display: none;
}
.mo {
  display: block;
}
.section1 {
  background: none;
}
/* Banner Movil */
.bannermv {
  width: 100vw;
  height: 145.41062801932367vw;
}
.bannerpc {
  display: none;
}
/* Cambiar fondo movil nosotros aqui */
.filanosotros {
  background: url(../assets/fondos1mv.svg);
  background-repeat: no-repeat;
  background-size: cover;
  margin-top: 0;
  padding-bottom: 111.353vw;
}
.idsecc {
  display: flex;
  width: 40%;
  margin: 0 auto 0;
  padding-top: 14.492753623188406vw;
}
.sectionsucursales .idsecc h5 {
  color: var(--co-h51seccion);
}
.sectionsucursales .idsecc hr {
  background: var(--co-hr2seccion);
  border-color: var(--co-hr2seccion);
}
.sectionsucursales .matriz-cont {
  display: flex;
  flex-direction: column;
  align-items: center;
  padding-top: 26.329vw;
}
.sectionsucursales .matriz-cont .tl {
  font-family: var(--font-titulo1);
  font-style: normal;
  font-weight: 400;
  font-size: 8.454vw;
  line-height: 90.5%;
  text-align: center;
  color: #ff4713;
  margin: 0;
}
.sectionsucursales .matriz-cont p.subtl {
  font-weight: 600;
  font-size: 4.348vw;
  line-height: 115.5%;
  text-align: center;
  color: #d9d9d9;
  width: 85.024vw;
  margin: 4.831vw 0 9.662vw;
  font-family: var(--font-txtcon);
}
.sectionsucursales .matriz-cont .threeitems {
  width: 50.039vw;
}
.sectionsucursales .matriz-cont .item {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-bottom: 7.971vw;
}
.sectionsucursales .matriz-cont .item img {
  width: 19.324vw;
  height: 19.324vw;
  margin-bottom: 4.589vw;
}
.sectionsucursales .matriz-cont .item p,
.sectionsucursales .matriz-cont .item a {
  font-family: var(--font-parrafo2);
  font-weight: 400;
  font-size: 3.382vw;
  line-height: 111%;
  text-align: center;
  color: #8e8e8e;
  margin: 0;
}
.imgqs1pc {
  display: none;
}
.imgqs1mv {
  width: 100vw;
  height: 67.15vw;
  padding-bottom: 16.908vw;
  margin-top: 0;
}
.idsecc h5 {
  font-size: var(--fs-idseccionmv);
  font-family: var(--font-titulo2);
  text-transform: uppercase;
  color: var(--co-hr1seccion);
  margin: 0;
  font-weight: 600;
}
.idsecc h5:nth-child(1) {
  font-weight: 800;
}
.idsecc .hr {
  width: 14.975845410628018vw;
  border: 0.078vw solid var(--co-hr1seccion);
  margin-top: 1.4vw;
  background: var(--co-hr1seccion);
  height: 0.04vw;
    margin-left: 3vw;
    margin-right: 3vw;
}
.menu-p .c-1 .p.var {
  text-transform: lowercase;
}
.bloqueqs {
  text-align: center;
  padding-top: 23.67149758454106vw;
}
.bloqueqs .nos1 {
  width: 54.191vw;
  margin: 0 12.802vw 4.662vw;
}
.bloqueqs .nos1.mo {
  display: block;
}
.bloqueqs .nos1.pc {
  display: none;
}
.bloqueqs h2 {
  font-size: var(--fs-t1nosomv);
  color: var(--co-t1noso);
  font-family: var(--font-titulo1);
  line-height: 7.64975845410628vw;
  letter-spacing: 0.03em;
  width: 82%;
  margin: auto;
  margin-bottom: 6.522vw;
  font-weight: 700;
  padding-left: 2vw;
  text-align: center;
}
.bloqueqs h4 {
  font-size: var(--fs-p1nosomv);
  font-family: var(--font-parrafo);
  line-height: 5.021739130434782vw;
  color: var(--co-p1noso);
  text-align: left;
  width: 75%;
  margin: auto;
  margin-bottom: 8.695652173913043vw;
}
.bloqueqs p {
  font-family: var(--font-parrafo);
  font-size: var(--fs-p2nosomv);
  color: var(--co-p2noso);
  line-height: 4.905797101449275vw;
  font-weight: 400;
  text-align: left;
  width: 74%;
  margin: auto;
  margin-bottom: 4.719806763285vw;
}
.bloqueqs p.orp {
  color: var(--co-p3noso);
  font-weight: 700; 
}
.bloqueqs .mb2 {
  margin-bottom: 10.145vw;
}
/* Seccion Servicios */
.sectionservicios {
  background: var(--co-bgservicios);
  width: 100%;
  height: fit-content;
}
.sectionservicios .servs-c {
  padding-bottom: 30.676vw;
}
.sectionservicios .idsecc h5 {
  color: var(--co-h52seccion);
  text-transform: uppercase;
}
.titservicios {
  text-align: center;
  color: var(--co-t1serv);
  margin: 0;
  margin-top: 20.048309178743963vw;
  margin-bottom: 10.144927536231885VW;
  font-size: var(--fs-t1servmv);
  font-family: var(--font-titulo1);
  font-weight: 700;
  padding-left: 15vw;
    padding-right: 15vw;
}
.sectionservicios .serv-item {
  width: 65.821vw;
  margin: 0 auto 8.696vw;
  display: flex;
  flex-direction: column;
  align-items: center;
}
.sectionservicios .servs-c.dir-c {
  width: 91.546vw;
  margin: auto;
}
.sectionservicios .dir-c .serv-item {
  width: 91.546vw;
}
.sectionservicios .dir-c .serv-item img {
  width: 48.792vw;
}
.sectionservicios .dir-c .stl {
  width: 80%;
}
.sectionservicios .dir-c a.btn {
  width: 71.498vw;
}
.sectionservicios .serv-item img {
  width: 100%;
}
.sectionservicios .tl {
  font-family: var(--font-titulo1);
  color: var(--co-t1serv);
  font-weight: 700;
  font-size: 6.280193236714976VW;
  line-height: 111%;
  text-align: center;
  margin: 4.348vw 0;
}
.sectionservicios .stl {
  font-weight: 300;
  font-size: 3.865vw;
  line-height: 4.831vw;
  color: var(--co-t2serv);
  text-align: center;
  width: 52.899vw;
  margin: 0 auto 4.348vw;
}
.sectionservicios a.btn {
  width: 71.49758454106279VW;
}
.sectionservicios a.btn div {
  width: 71.49758454106279VW;
  margin: auto;
  border: 0.5vw solid var(--co-third);
  color: var(--co-third);
  padding: 6.763vw 0;
  text-align: center;
  border-radius: 100vw;
  font-weight: 800;
  font-size: 4.348vw;
  transition: .5s;
}
.sectionservicios a.btn div:hover{
  background-color:  var(--co-third);
  color: white;
}
.sectionservicios a.btn.prox {
  pointer-events: none;
}
.sectionservicios a.btn.prox div {
  border: 0.1vw solid var(--co-prox1);
  color: var(--co-prox2);
  background-color: var(--co-prox1);
  font-weight: 500;
}
.subservicios {
  text-align: center;
  color: var(--co-t2serv);
  font-family: var(--Inter);
  font-size: var(--fs-t2servmv);
  line-height: 5.021739130434782vw;
  font-weight: 400;
  /*width: 85%;*/
  width: 83%;
  margin: auto;
  margin-top: 9.903381642512077vw;
  margin-bottom: 16.908212560386474VW;
}
.subservicios span {
  cursor: pointer;
}
.bloqueservicio {
  text-align: center;
}
.bloqueservicio img {
  width: 68.11594202898551vw;
  height: 52.65700483091788vw;
}
.bloqueservicio h3 {
  color: var(--co-h3serv);
  font-size: var(--fs-h3servmv);
  font-family: var(--font-titulo1);
  width: 70%;
  margin: auto;
  margin-top: 4.3478260869565215vw;
  line-height: 5.898550724637682vw;
}
.bloqueservicio p {
  text-align: left;
  width: 60%;
  margin: auto;
  margin-top: 4.3478260869565215vw;
  font-size: var(--fs-pservmv);
  font-family: var(--font-parrafo);
  color: var(--co-pserv);
  margin-bottom: 5.314vw; /**/
  line-height: 4.826086956521739vws;
}
.bloquevermas {
  text-align: center;
  margin-top: 12.734299516908212vw;
  padding-bottom: 16.425120772946862vw;
}
.bloquevermas p {
  color: var(--co-btnserv);
  font-family: var(--font-parrafo);
}
/* Seccion contacto */
.col1-s3 {
  display: none;
}
.col2-s3 {
  background-image: url(../assets/fondocontacto.svg);
  background-size: 100%;
}
.sectioncontacto {
  background-color: #fa8433;
  overflow: hidden;
  /*display: flex;*/
}
.sectioncontacto .idsecc h5 {
  color: #005cb9;
}
.sectioncontacto .idsecc .hr {
  background: var(--co-hr2seccion);
  border: 0.078vw solid #005cb9;
}
.sectioncontacto h2 {
  text-align: center;
  margin: 0;
  font-size: var(--fs-titcontamv);
  color: #005cb9;
}
.sectioncontacto .titc1 {
  font-family: var(--font-titulo2);
  margin-top: 23.91304347826087vw;
  color: var(--co-titconta1);
  font-size: var(--fs-titconta1mv);
  line-height: 7.64975845410628vw;
}

.sectioncontacto .titc2 {
  font-family: var(--font-titulo1);
  color: var(--co-titconta);
  font-size: var(--fs-titcontamv);
  line-height: 9.83574879227053vw;
}
.sectioncontacto h4 {
  text-align: center;
  font-family: var(--font-parrafo);
  font-size: var(--fs-subcontamv);
  font-weight: 400;
  width: 80%;
  margin: auto;
  margin-top: 4.1062801932367154vw;
  line-height: 5.579710144927537vw;
}
.sectioncontacto h4 span {
  font-weight: 600;
}
.filadacon {
  margin-top: 9.66183574879227vw;
  text-align: center;
}
.filadacon img {
  width: 19.32367149758454vw;
  height: 19.32367149758454vw;
}
.filadacon p {
  font-family: var(--font-parrafo);
  font-size: var(--fs-pacontamv);
  font-weight: 400;
  margin: 0;
  margin-top: 3.5vw;
  margin-bottom: 16.425120772946862vw;
}
.filadacon p span {
  font-weight: 600;
}
.filadaubi {
  text-align: center;
  padding-bottom: 16vw;
}
.filadaubi img {
  margin-bottom: 3.5vw;
  width: 19.32367149758454vw;
  height: 19.32367149758454vw;
}
.filadaubi p {
  font-family: var(--font-parrafo);
  font-size: var(--fs-pacontamv);
  font-weight: 400;
  margin: 0;
  line-height: 5.36231884057971vw;
}
.nameubi {
  font-weight: 700 !important;
}
.direubi {
  width: 80%;
  margin: auto !important;
  margin-bottom: 3.5vw !important;
}
.mapamv {
  height: 78.74396135265701vw;
}
/* */
.bloquepromo {
  height: fit-content;
  overflow: hidden;
}
.bloquepromo img {
  width: 100%;
  height: auto;
  object-fit: cover;
}
/* Seccion Siguenos */
.sectionredes {
  background-color: #f7e3db;
  /*background-image: url("../assets/lefonde.png");
  background-size: 100%;
  background-position-y: bottom;
  padding-bottom: 11.11111111111111vw;*/
  padding-bottom: 21.111111vw;
}
.sectionredes .idsecc h5 {
  color: var(--co-h53seccion);
}
.sectionredes .idsecc .hr {
  background: var(--co-hr3seccion);
  border: 0.078vw solid var(--co-hr3seccion);
}
.sectionredes h2 {
  margin: auto;
  font-family: var(--font-titulo1);
  font-weight: 700;
  color: var(--co-titsig);
  text-align: center;
  font-size: var(--fs-titsigmv);
  margin-top: 20.048309178743963vw;
  margin-bottom: 5vw;
  text-transform: inherit;
  width: 70%;
}
.sectionredes .txtredes {
  margin: auto;
  color: var(--co-txtsig);
  text-align: center;
  width: 73%;
  font-weight: 400;
  font-family: var(--font-parrafo);
}
.fila-br {
  width: 91%;
  margin: auto;
  margin-top: 12vw;
  margin-bottom: 17vw;
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}
.fila-br .fbr {
  width: 41.21256038647343vw;
  height: 41.21256038647343vw;
  margin-bottom: 5vw;
  overflow: hidden;
}
.fila-br img {
  width: 41.21256038647343vw;
  height: 41.21256038647343vw;
}
.img2br {
  margin-left: 5vw;
}
.btnig {
  display: flex;
  background-image: url(../assets/logoig.svg);
  background-size: 7.770531400966184vw 8.007246376811594vw;
  background-repeat: no-repeat;
  background-position-x: 22%;
  background-position-y: 50%;
  text-align: center;
  width: 74.155vw;
  margin: auto;
  border: 0.2vw solid #1E7E8B;
  border-radius: 12vw;
  background-color: transparent;
  transition: 0.5s;
  background-color: transparent;
}
.btnig h5 {
  font-weight: 800; 
  width: 100%;
  text-align: center;
  border-radius: 1.4492753623188406vw;
  font-family: var(--font-titulo1);
  font-size: var(--fs-btnigmv);
  font-weight: 700;
  margin: 0;
  margin-top: 4.830917874396135vw;
  margin-bottom: 4.830917874396135vw;
  color: #1E7E8B;
} 
.imgban2pc {
  display: none;
}
.imgban2mv {
  width: 100%;
  height: auto;
}
/* Seccion Formulario */
.sectionformulario {
  padding-top: 20.77294685990338vw;
  padding-bottom: 17.632850241545896vw;
}
.sectionformulario h2 {
  text-align: left;
  font-family: "Inter";
  font-size: var(--fs-titformmv);
  color: var(--co-titformmv);
  font-weight: 700;
  color: #f7e3db;
  width: 71vw;
  margin: 0 auto 6.560386vw;
}
.sectionformulario p.txt-ctc {
  width: 71%;
  margin: auto;
  font-style: normal;
  font-weight: 400;
  line-height: 111%;
  color: white;
  font-family: var(--font-parrafo);
  font-size: var(--fs-adpformmv);
  line-height: 7.2vw;
  margin-bottom: 10.281vw;
}
.bloqueform {
  width: 71%;
  margin: auto;
}
.inputbf {
  width: 100%;
  height: 14.975845410628018vw;
  margin-bottom: 5.381643vw;
  border: 0.362vw solid transparent;
  text-indent: 5%;
font-family: 'Outfit';
  font-size: var(--fs-inpformmv);
  color: #1e7e8b;
  border-radius: 8vw;
  background-color: #f7e3db;
  font-weight: 400;
}
.inputbf::placeholder {
  color: #1e7e8b;
  font-weight: 400;
}
.texa {
  width: 100%;
  background-color: #f7e3db;
  margin-bottom: 3.3816425120772946vw;
  border: 0.362vw solid transparent;
  text-indent: 5%;
  padding-top: 5vw;
font-family: 'Outfit';
  font-size: var(--fs-inpformmv);
  line-height: 4.676328502415459vw;
  color: #1e7e8b;
  height: 29.71vw;
  resize: none;
  border-radius: 8vw;
  font-weight: 400;
}
.texa::placeholder {
  color: #1e7e8b;
  font-weight: 400;
}
.bloqueaviso {
  display: flex;
}
.bloqueaviso .inpcheck {
  width: 3.6231884057971016vw;
  height: 3.6231884057971016vw;
  margin-right: 2.5vw;
  border: .1vw solid white;
    display: flex;
    align-items: center;
    justify-content: center;
}
  .bloqueaviso .inpcheck .checked {
    background: white;
  width: 3.3231884057971016vw;
  height: 3.3231884057971016vw;
}
.bloqueaviso .txtaviso {
  margin: 0;
  font-family: var(--font-parrafo2);
  font-size: var(--fs-adpformmv);
  color: var(--co-adpform);
  line-height: 7.5724637681159415vw;
  margin-bottom: 9.420289855072465vw;
    width: 70vw;
}
.txtaviso a {
  color: var(--co-linkadpform);
  text-decoration: none;
}
button.btnform {
  width: 100%;
  border: none;
  background: transparent;
  cursor: pointer;
}
.btnform p {
  background: var(--co-btnform);
  color: var(--co-pabtnform);
  text-align: center;
  border: 0.21vw solid var(--co-pabtnform);
  font-family: var(--font-parrafo);
  font-size: var(--fs-pabtnformmv);
  font-weight: 700;
  padding: 7.488vw 0 6.763vw;
  border-radius: 12vw;
  margin: 0;
  transition: 0.5s;
}
.btnform p:hover {
  background: #F7E3DB;
  color: #FA8433;
    border: 0.13vw solid #FA8433;
}
.sectionsucursales {
  padding-bottom: 10vw;
}
.bloquesucursales h2 {
  text-align: center;
  color: var(--co-titsucu);
  font-size: var(--fs-titsucumv);
  font-family: var(--font-titulo1);
  margin: 0;
  margin-top: 22.222vw;
  margin-bottom: 20.6458333333333335vw;
  font-weight: 400;
}
.bloquebtnubi {
  text-align: center;
}
.bloquebtnubi a p {
  font-family: var(--font-titulo1);
  color: var(--co-txtbtnsu);
  font-size: var(--fs-txtbtnsumv);
  line-height: 5.386473429951691vw;
  width: 40%;
  margin: auto;
  border: 1px solid #0017c5;
  padding: 4.831vw 20vw 4.831vw 20vw;
  border-radius: 10vw;
  margin-bottom: 19.32367149758454vw;
  transition: 0.5s;
}
.bloquebtnubi a p:hover {
  color: white;
  background-color: #0017c5;
}
.slidepc {
  display: none;
}
.bannermenupc {
  display: none;
}
img.slidemv {
  width: 100%;
}
.Navigator {
  position: fixed;
  padding: 0 0 0 0;
  width: 100%;
  z-index: 599;
}
.sectionservicios .idsecc .hr {
  background: var(--co-hr2seccion);
  border: 0.078vw solid var(--co-hr2seccion);
}
.bloquebanmenu {
  text-align: center;
}
img.bannermenumv {
  width: 95%;
}
.imgpromopc {
  display: none;
}

.F7 {
  width: 68.357vw;
  margin: auto;
}
.Desktop {
  display: none;
}
.F7Content {
  margin-bottom: 24.396135265700483vw;
}
img.F7I1 {
  width: 68.357vw;
  height: 47.58454106280193vw;
  border-radius: 5vw;
  margin-bottom: 10.38647342995169vw;
}
p.F7T1 {
  font-size: 6.280193236714976vw;
  font-weight: 600;
  color: var(--co-titsucu);
  font-family: var(--font-titulo2);
  margin: 0vw;
  margin-bottom: 4.1062801932367154vw;
}
p.F7T2 {
  margin-bottom: 6.1062801932367154vw !important;
  min-height: 11vw;
}
p.F7T {
  font-size: var(--fs-txtsucumv);
  line-height: 4.855072463768116vw;
  font-weight: 400;
  color: var(--co-txtsucu);
  font-family: var(--font-parrafo2);
  margin: 0vw;
  width: 72vw;
}
.F7F3 {
  display: flex;
  width: 68.357vw;
  height: 17.632850241545896vw;
  background-color: var(--fo-btnwhasu);
  border-radius: 12vw;
  align-items: center;
  justify-content: center;
  margin-top: 11.11111111111111vw;
  cursor: pointer;
  transition: 0.5s;
}
.F7F3:hover {
  background-color: var(--color-2);
}
.F7F3 img {
  width: 6.763285024154589vw;
  height: 6.763285024154589vw;
  margin-right: 4.5893719806763285vw;
  filter: brightness(1);
  transition: 0.5s;
}
.F7F3:hover img {
  filter: brightness(10);
}
.F7F3 p {
  font-size: 4.830917874396135vw;
  font-weight: 600;
  font-family: var(--font-parrafo);
  margin: 0vw;
  color: #ffffff;
}
.sectiontiktok {
  background: url(../assets/tiktokfondomv.png);
  background-size: cover;
  background-repeat: no-repeat;
  background-position-y: bottom;
  text-align: center;
  padding-bottom: 128vw;
}
.cotik {
  color: var(--co-h53seccion) !important;
}
.sectiontiktok .idsecc .hr {
  background: var(--co-hr3seccion);
  border: 0.078vw solid var(--co-hr3seccion);
}
.flexic .formimg {
  width: 87.198vw;
  margin: 0 0 0 auto;
}
.flexic .formimg.mo {
  display: block;
}
.flexic .formimg.pc {
  display: none;
}
.bloquetiktok h2 {
  color: var(--co-txttik);
  font-family: var(--font-titulo1);
  text-align: center;
  margin: 0;
  margin-top: 19.32367149758454vw;
  margin-bottom: 6.763285024154589vw;
  font-weight: 400 !important;
}
.bloquetiktok img {
  width: 71.98067632850241vw;
  height: auto;
  margin-bottom: 11.83574879227053vw;
}
.bloquetiktok h6 {
  color: var(--co-txttik);
  font-family: var(--font-titulo1);
  font-size: var(--fs-txth5mv);
  width: 60%;
  margin-top: 0;
  margin-bottom: 0;
  margin: auto;
}
.bloquebtntik p {
  color: var(--co-txtbtntik);
  font-family: var(--font-titulo1);
  font-size: var(--fs-btntik);
  background: #ffa400;
  width: fit-content;
  padding: 5.797vw 15.2vw 5.797vw 23.2vw;
  border-radius: 30vw;
  margin: auto;
  margin-top: 7.5vw;
  margin-bottom: 4vw;
  background-image: url("../assets/ttk.svg");
  background-repeat: no-repeat;
  background-size: 5.072vw;
  background-position-y: 5.556vw;
  background-position-x: 13.285vw;
  transition: 0.5s;
}

/*.bloquebtntik p:hover {
  background-color: var(--color-2);
}*/
.placa-v {
  display: none;
}
.modal-container {
  opacity: 1;
  transition: 0.5s;
  position: relative;
  z-index: 1200;
}
.nonemodal {
  opacity: 0;
  pointer-events: none;
}
@media (max-width: 1024px) {
.bloqueqs p.orp.tl { 
font-size: 4.831vw;
}
  
  .section1 .slidemain{ 
    overflow: hidden;
    height: 177vw;
  }
  .sectionsucursales {
    padding-bottom: 0;
  }
  .mapcont {
    width: 100%;
    height: 78.744vw;
  }
  .videoc {
    margin-top: 20.773vw;
  }
  .btnvi {
    position: absolute;
    width: 36.473vw;
  }

  .sectionredes .idsecc {
    width: 50%;
  }
  /*.filanosotros .idsecc {
    display: flex;
    width: 55%;
    margin: 0 auto 0 13.043vw;
    padding-top: 14.492753623188406vw;
  }*/
  .bloquepromo .contpc {
    display: none;
  }
  .bloquepromo .contmo {
    display: flex;
  }
  .btnig h5 {
    position: relative;
    left: 5vw;
    font-weight: 700;
  }
  div#Home {
    width: 100%;
    overflow: hidden;
  }
  .menu-pc {
    display: none;
  }
  .menu-mo {
    display: block;
  }

  .img3br,
  .img4br {
    margin-bottom: 0 !important;
  }
  .menu-p .nota {
    margin: 4.3vw 0 !important;
  }
  :deep(.menu-p .nota > p) {
    font-size: 4.348vw !important;
    line-height: 5.3vw;
  }
  .sectionbanner8 {
    display: flex;
    height: auto;
  }
  .flexic {
    display: flex;
    flex-direction: column;
    align-items: center;
  }
  .bloquetiktok h6 {
    margin: auto auto 12.493vw;
    font-weight: 400 !important;
  }
  .menu-p p.subc {
    font-style: normal;
    font-weight: 400;
    font-size: 4.348vw;
    line-height: 111%;
    color: #8e8e8e;
    text-align: center;
  }
  .section1 .col2-qs {
    display: grid;
  }
  .col1-qs .btnvi {
    display: none;
  }
  .sectionformulario .titform.pc {
    display: none;
  }
  .sectionformulario .titform.mo {
    display: block;
  }
}

:deep(.menu-p .nota > p span) {
  font-weight: 700;
  color: #02a550;
}
.videoc {
  display: flex;
  align-items: center;
  justify-content: center;
}






@media (min-width: 1024px) {
.subservicios br{
  display: none;
}
  .fs3{
    font-size: var(--fs-p2noso2)!important;
  }
  .sectionformulario .titform.pc {
    display: block;
  }
  .sectionformulario .titform.mo {
    display: none;
  }
  .cartbtn {
    width: 2.344vw;
    height: 2.061vw;
    background-image: url("../assets/cart.svg");
    background-size: 100%;
    background-repeat: no-repeat;
    cursor: pointer;
    transition: 0.5s;
  }
  .cartbtn:hover {
    background-image: url("../assets/cartylw.svg");
  }
  .ylw {
    background-image: url("../assets/cartylw.svg");
  }
  .mapcont {
    width: 100%;
    height: 26.875vw;
  }
  .videoc {
    display: none;
  }
  .sectiontiktok .idsecc {
    display: none;
  }

  .bloquepromo .contpc {
    display: flex;
  }
  .bloquepromo .contmo {
    display: none;
  }
  .menu-p .imgtxt-c {
    display: flex;
  }
  .menu-p .txt-c {
    width: auto;
    padding-left: 0.885vw;
  }
  .menu-p .product-img {
    width: 4.479vw;
    height: 4.479vw;
  }
  .menu-p p.subc {
    font-weight: 500;
    color: #8e8e8e;
    font-family: var(--font-parrafo2);
  }
  .cat-it .nota p {
    margin-top: 1vw;
  }
  :deep(.menu-p .nota > p) {
    font-size: 0.7vw;
    line-height: 0.94vw;
    color: gray;
    margin-top: 0.6vw;
  }
  .menu-p .menu-list {
    width: 55vw;
    margin: 4.271vw 0 0 auto;
    display: flex;
    flex-wrap: wrap;
    flex-direction: row;
  }
  .menu-p p.subc {
    font-size: 0.833vw;
    line-height: 1.133vw;
    padding: 0.885vw 0 2.474vw;
  }
  .menu-p .cart {
    width: 2.474vw;
    height: 2.061vw;
    transition: 0.5s;
    cursor: pointer;
    filter: invert(24%) sepia(97%) saturate(1382%) hue-rotate(191deg)
      brightness(97%) contrast(108%);
  }
  .menu-p .cart.ylw {
    filter: invert(66%) sepia(49%) saturate(2801%) hue-rotate(0deg)
      brightness(103%) contrast(104%);
  }

  .menu-p .cart:hover {
    filter: invert(66%) sepia(49%) saturate(2801%) hue-rotate(0deg)
      brightness(103%) contrast(104%);
  }
  .cat-it {
    display: flex;
  }
  /*.cat-it.catflex {
    justify-content: space-between;
  }*/
  .cat-it .tl {
    font-family: var(--font-titulo1);
    font-style: normal;
    font-weight: 800;
    font-size: 2.083vw;
    line-height: 90.5%;
    color: #c5c5c5;
    cursor: pointer;
    margin: 0 4.302vw 1.2vw 0;
    transition: 0.5s;
  }
  .cat-it .tl:hover {
    color: var(--c-cathover-menu) !important;
  }
  .cat-it .tl.act {
    color: var(--c-cathover-menu) !important;
  }
  .cat-it .sublist {
    display: flex;
    width: 100%;
  }
  .cat-it .sublist .stl {
    font-family: var(--font-titulo1);
    font-style: normal;
    font-weight: 800;
    font-size: 1.042vw;
    line-height: 90.5%;
    margin: 0 3.8vw 0 0;
    color: #c5c5c5;
    cursor: pointer;
    transition: 0.5s;
  }
  .cat-it .sublist .stl:hover {
    color: #fdcd0a !important;
  }
  .cat-it .sublist .stl.act {
    color: #fdcd0a !important;
  }
  .menu-pc {
    display: block;
    width: 100%;
  }
  .menu-mo {
    display: none;
  }
  .F7 {
    width: 70vw;
  }

  .Mobil {
    display: none;
  }
  .Desktop {
    display: flex !important;
    flex-flow: wrap;
    justify-content: space-between;
  }

  .F7Content {
    width: 19.010416666666664vw;
    margin-bottom: 8.59375vw;
    transform: scale(1);
    transition: 0.5s;
    margin-right: 7.083333333333333vw;
  }
  .F7Content:hover {
    transform: scale(1.05);
  }
  img.F7I1 {
    width: 19.739583333333332vw;
    height: 13.750000000000002vw;
    border-radius: 1.08vw;
    margin-bottom: 3.75vw;
  }
  p.F7T1 {
    font-size: 1.3541666666666667vw;
    margin-bottom: 0.8854166666666666vw;
  }
  p.F7T {
    font-size: 0.9375vw;
    line-height: 1.25625vw;
    width: auto;
  }
  p.F7T2 {
    margin-bottom: 2vw !important;
    min-height: 1.56vw;
  }

  .F7F3 {
    width: 15.729166666666666vw;
    height: 3.802vw;
    margin-top: 2.083333333333333vw;
  }
  .F7F3 img {
    width: 1.4583333333333333vw;
    height: 1.4583333333333333vw;
    margin-right: 0.9895833333333333vw;
  }
  .F7F3 p {
    font-size: 0.98vw;
  }

  .pc {
    display: block;
  }
  .mo {
    display: none;
  }
  /* Cambiar fondo Seccion 1 aqui */
  .section1 {
    background-image: url(../assets/fondos1.svg);
    background-size: cover;
    background: none !important;
  }
  .Navigator {
    position: fixed;
    padding: 0 0 0 0;
    width: 100%;
    z-index: 599;
  }
  .slidepc {
    display: block;
  }
  .slidemv {
    display: none;
  }
  .slidemain img {
    width: 100%;
    cursor: grab;
  }
  .filanosotros {
    background: url(../assets/fondonoso.svg);
    background-color: #005cb9;
    background-size: cover;
    background-repeat: no-repeat;
    padding-bottom: 0vw;
    margin-top: 0;
  }
  .bloqueqs .mb2 {
    margin-bottom: 2.24vw;
  }
  .bloqueqs .w50qs {
    width: 15.375vw;
  }
  .bloqueqs .nos1 {
    width: 17.288vw;
    margin: 3.021vw 0 4.662vw;
  }
  .filanosotros .mt3 {
    margin: 3.021vw 0 0;
}
  .bloqueqs .nos1.mo {
    display: none;
  }
  .bloqueqs .nos1.pc {
    display: block;
  }
  .bannermenupc {
    display: block;
  }
  .bannermenumv {
    display: none;
  }
  .filabanner {
    text-align: left;
    margin: auto;
  }
  .bannermv {
    display: none;
  }
  .bannerpc {
    display: block;
    width: 89.73958333333333vw;
    height: 38.4375vw;
    margin: auto;
  }
  .imgqs1pc {
    display: block;
  }
  .imgqs1mv {
    display: none;
  }
  .idsecc {
    display: flex;
    width: 13%;
    margin: auto;
    padding-top: 4.74vw;
  }
  .idsecc h5 {
    font-size: var(--fs-idseccionpc);
    margin: 0;
  }
  .idsecc .hr {
    width: 3.229166666666667vw;
    background: var(--co-hr1seccion);
    border: 0.078vw solid var(--co-hr1seccion);
    margin-top: 0.35vw;
    height: 0.01vw;
    margin-left: 1.3vw;
    margin-right: 1.3vw;
  }
  .filanosotros .idsecc {
    display: flex;
    width: 13%;
    margin: 0 auto 0 56vw;
    padding-top: 4.688vw;
  }
  .bloqueqs {
    padding-top: 8.125vw;
    padding-bottom: 7.292vw;
    display: flex;
    /* background-image: url("../assets/huevitos.png");
    background-size: 32.917vw;
    background-repeat: no-repeat;
    background-position-x: 60.625vw;
    background-position-y: 29.375vw;*/
  }
  .col1-qs {
    width: 48.958vw;
    display: flex;
    justify-content: center;
    align-items: flex-end;
  }
  .btnvi {
    width: 11.615vw;
    cursor: pointer;
  }
  .imgqs1pc {
    width: 37.135416666666664vw;
    height: 35.989583333333336vw;
  }
  .col2-qs {
    height: 35.969vw;
    width: 36.1896vw;
    padding-left: 6.406vw;
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    justify-content: space-between;
  }
  .bloqueqs p.orp{
    font-weight: 700;
  }
  .bloqueqs h2 {
    padding-top: 0;
    font-size: var(--fs-t1noso);
    color: var(--co-t1noso);
    text-align: left;
    line-height: 2.3567708333333335vw;
    margin-bottom: 2.604vw;
    margin: 0 auto 2.604vw 0;
    padding-left: 0;
    width: auto;
  }
  .bloqueqs h4 {
    margin: 0;
    font-size: var(--fs-p1noso);
    line-height: 1.203125vw;
    margin-bottom: 3vw;
    margin-left: 4vw;
    width: 74%;
  }
  .bloqueqs p {
    font-size: var(--fs-p2noso);
    margin: 0;
    width: auto;
    /*width: 79%;*/
    line-height: 126.5%;
    margin-left: 0vw;
    margin-bottom: 0.99vw;
    text-align: left;
    letter-spacing: 0.01em;
  }
  .bloqueqs p:last-child {
    margin-left: 0vw;
  }
  /* Seccion Servicios */
  .titservicios {
    margin-top: 8.75vw;
    margin-bottom: 4.271vw;
    font-size: var(--fs-t1serv);
    letter-spacing: 0.01em;
    line-height: 3.440625vw; 
  font-weight: 800;
  }
  .subservicios {
    font-size: var(--fs-t2serv);
    font-weight: 600;
    line-height: 1.2406250000000001vw;
    margin: auto !important;
    margin-top: 1.54166666666665vw !important;
    text-align: center;
    width: 43% !important;
  }
  .slideservicios {
    display: flex;
    width: 60%;
    margin: auto;
    margin-top: 7.656250000000001vw;
    padding-bottom: 3.427vw;
    height: fit-content !important;
  }
  .sectionservicios .serv-item {
    width: 11.406vw;
    margin: 0 1.823vw;
  }
  .sectionservicios .tl {
    font-size: 1.042vw;
    margin: 2.031vw 0 0;
  }
  .sectionservicios .stl {
    font-size: 0.729vw;
    line-height: 0.938vw;
    width: 100%;
    margin: 0.938vw auto;
    font-weight: 400;
  color: var(--co-t2servpc);
  }
  .sectionservicios .dir-c .stl{
    width: 95%;
    margin: 0.938vw auto 0;
    font-size: 0.938vw;
    color: var(--co-t2serv);
  }
  .sectionservicios .dir-c .stl.tl2{
    color: var(--co-t2serv);
  }
  .sectionservicios a.btn div {
    width: 23.541666666666668VW;
    border: 0.1vw solid var(--co-third);
    color: var(--co-third);
    /*padding: 1.094vw 0;*/ 
    padding: 1.719vw 0;
    text-align: center;
    border-radius: 100vw;
    font-weight: 800;
    font-size: 0.729vw;
  }
  .sectionservicios .servs-c {
    padding-bottom: 9.427vw;
    display: flex;
    justify-content: center;
  }
  .sectionservicios .dir-c .tl  {
    font-size: 1.354vw;
    font-family: sans-serif;
}
  .sectionservicios .dir-c a.btn {
    width: 23.542vw;
  }
  .sectionservicios .dir-c a.btn div{
    font-size: 1.042vw;
  }
  .sectionservicios .dir-c .serv-item img {
    width: 10.521vw;
  }
  .sectionservicios .servs-c.dir-c {
    width: 46.041666666666664VW;
    margin-top: 6.667vw; 
    flex-direction: column;
    align-items: center;
  }
.sectionservicios .servs-c.dir-c .cdflx{ 
    display: flex;
    width: 100%;
    justify-content: space-evenly;
}
  .sectionservicios .dir-c .serv-item {
    width: 19.74vw;
    margin: 0 3.281vw 9.792vw;
  }
  .bloqueservicio img {
    width: 11.354166666666666vw;
    height: 11.354166666666666vw;
  }
  .bloqueservicio h3 {
    font-size: var(--fs-h3serv);
    line-height: 1.0984375vw;
    width: 60%;
    margin: auto;
    margin-top: 0.9375vw;
  }
  .bloqueservicio p {
    text-align: left;
    width: 80%;
    margin: auto;
    margin-top: 0.9375vw;
    font-size: var(--fs-pserv);
    color: var(--co-pserv);
    /*margin-bottom: 5.314009661835748vw;*/
    line-height: 0.8093750000000001vw;
  }
  .bloquebanmenu {
    text-align: center;
  }
  .bannermenupc {
    width: 61.82291666666667vw;
    height: 21.624479166666667vw;
    padding-top: 7.604vw;
    margin: auto;
  }
  .bloquevermas {
    display: none;
  }
  /* Seccion Contacto */
  .col1-s3 {
    display: block;
  }
  .mapamv {
    display: none;
  }

  .col1-s3 {
    width: 42%;
  }
  .col2-s3 {
    width: 58%;
    padding-left: 8.333333333333332vw;
  }
  .sectioncontacto .idsecc {
    margin: auto;
    width: 12%;
  }
  .sectioncontacto .titc1 {
    margin-top: 9.270833333333334vw;
    font-size: var(--fs-titconta1);
    line-height: 2.5921875vw;
    text-align: left;
  }
  .sectioncontacto .titc2 {
    font-size: var(--fs-titconta);
    line-height: 2.5921875vw;
    text-align: left;
  }
  .sectioncontacto h4 {
    text-align: left;
    font-size: var(--fs-subconta);
    font-weight: 400;
    width: auto;
    margin-top: 1.4583333333333333vw;
    line-height: 1.203125vw;
    margin-left: 4vw;
  }
  .filadacon {
    display: flex;
    margin-top: 2.604166666666667vw;
    margin-left: 4vw;
  }
  .col1-dc,
  .col2-dc,
  .filadaubi {
    display: flex;
  }
  .col2-du {
    margin-top: 1.8vw;
  }

  .filadacon img,
  .filadaubi img {
    width: 4.427083333333334vw;
    height: 4.427083333333334vw;
    margin-right: 1.5625vw;
  }
  .filadacon p {
    font-size: var(--fs-paconta);
    font-weight: 400;
    margin: 0;
    margin-top: 1.8vw;
    margin-bottom: 2vw;
    margin-right: 3vw;
  }
  .filadaubi {
    margin-left: 4vw;
    margin-top: 1.875vw;
  }
  .filadaubi p {
    font-size: var(--fs-paconta);
    margin: 0;
    line-height: 1.36231884057971vw;
    text-align: left;
  }
  .direubi {
    width: 50%;
    margin: 0 !important;
    margin-bottom: 2vw !important;
  }
  /* */
  .bloquepromo {
    height: 21.9vw;
    overflow: hidden;
  }
  .bloquepromo img {
    width: 100%;
    height: 22vw;
    object-fit: cover;
  }
  /* Seccion siguenos */
  .sectionredes .idsecc {
    padding-top: 4.479166666666667vw;
  }
  .sectionredes h2 {
    font-size: var(--fs-titsig);
    margin-top: 4.78125vw;
    margin-bottom: 2.5520833333333335vw;
  }
  .sectionredes .txtredes {
    font-size: var(--fs-txtsig);
    width: 35%;
    font-weight: 400;
    line-height: 1.1979166666666667vw;
    margin-bottom: 3.073vw;
  }
  .fila-br .fbr {
    width: 13.802083333333334vw;
    height: 13.802083333333334vw;
    display: flex;
    align-items: center;
    justify-content: center;
    border-radius: 0;
    margin-bottom: 0;
  }
  .fila-br img {
    width: 13.802083333333334vw;
    height: 13.802083333333334vw;
    transition: 0.5s;
  }
  .fila-br .fbr:hover img {
    width: 16.802083333333334vw;
    height: 16.802083333333334vw;
  }
  .img2br,
  .img3br {
    margin-left: 2.65625vw;
  }
  .fila-br {
    width: fit-content;
    /*width: 70%;
    margin-bottom: 3.0208333333333335vw;*/
    margin: auto;
    margin-bottom: 0;
    flex-wrap: nowrap;
  }
  .sectionredes {
    background-color: #f7e3db;
    /*background-image: url("../assets/lefonde2.png");
    background-position-y: bottom;
    background-size: 100%;
    background-repeat: no-repeat;*/
    padding-bottom: 11.615vw;
  }
  .bloqueredes {
    padding-left: 0vw;
  }
  .bloquebtnig {
    display: flex;
  }
  .bloqueredes a {
    margin: 4.688vw auto 0;
    width: 13.229vw;
  }
  .btnig {
    display: flex;
    background-image: url(../assets/logoig.svg);
    background-size: 1.1989583333333333vw 1.2171875vw;
    background-repeat: no-repeat;
    background-position-x: 22%;
    background-position-y: 50%;
    text-align: center;
    width: 100%;
    margin: 0;
    border-radius: 2.5vw;
    border-width: 0.15vw;
  }
  .btnig:hover {
    background-color: #1E7E8B;
    background-image: url("../assets/logoig2.svg");
    background-size: 1.1989583333333333vw 1.2171875vw;
    background-repeat: no-repeat;
    background-position-x: 22%;
    background-position-y: 50%;
  border: 0.2vw solid #1E7E8B;
  }
  .btnig h5 {
    width: 100%;
    text-align: center;
    font-size: var(--fs-btnig);
    line-height: 1.5vw;
    margin: 0;
    margin-top:0.521vw;
    /*margin-top: 0.9770833333333334vw; */
    margin-bottom:0.521vw;
    position: relative;
    left: 0.8vw;
    transition: 0.5s;
  }
  .btnig:hover h5 {
    color: #F7E3DB !important;
  }
  .imgban2pc {
    display: block;
    width: 100%;
    height: 22.083333333333332vw;
  }
  .imgban2mv {
    display: none;
  }
  /* Seccion Formulario */
  .sectionformulario {
    /*padding-top: 8.072916666666668vw;*/
    width: 29.01vw;
    padding-top: 0;
    padding-bottom: 5.989583333333334vw;
    margin-right: 4.531vw;
    margin-top: 5.521vw;
  }
  .sectionformulario h2 {
    font-size: var(--fs-titform);
    font-family: "Outfit";

    margin: 0;
    margin-bottom: 1.823vw;
    font-weight: 700;
    line-height: 90.5%;
    text-align: left;
  }
  .sectioncontacto .flexic {
    display: flex;
    /*margin: 8.802vw auto 0;*/
    margin: 0 0 0 auto;
    width: 86.198vw;
  }
  .flexic .formimg {
    width: 52.188vw;
    height: 40.208vw;
  }
  .flexic .formimg.mo {
    display: none;
  }
  .flexic .formimg.pc {
    display: block;
    margin-top: 4.531vw;
  }
  .bloqueform {
    width: 29.01vw;
    margin: 0;
  }
  .inputbf {
    width: 100%;
    height: 3.229vw;
    margin-bottom: 0.729vw;
    border: 0.078vw solid transparent;
    text-indent: 3.5%;
    font-size: var(--fs-inpform);
    padding: 0;
  }
  .inputname {
    width: 100%;
    margin-right: 1.4583333333333333vw;
  }
  .inputnumber {
    width: 100%;
    margin-right: 1.4583333333333333vw;
  }
  .inputemail {
    width: 100%;
  }
  .texa {
    width: 100%;
    height: 5vw;
    margin-bottom: 1.146vw;
    border: 0.078vw solid #ffc700;
    text-indent: 3.5%;
    padding-top: 1.406vw;
    padding-left: 0;
    font-size: var(--fs-inpform);
    line-height: 1.0083333333333333vw;
    border-radius: 2vw;
  }
  .bloqueaviso {
    width: 100%;
    margin-bottom: 2.552vw;
    align-items: center;
  }
  .bloqueaviso .inpcheck {
    width: 0.8333333333333334vw;
    height: 0.8333333333333334vw;
    margin-right: 0.6770833333333334vw;
  }
  .bloqueaviso .inpcheck .checked {
    background: white;
    width: 0.5333333333333334vw;
    height: 0.5333333333333334vw;
}
  .bloqueaviso .txtaviso {
    margin: 0;
    font-size: var(--fs-adpform);
    line-height: 1.2703125000000002vw;
    margin-bottom: 0vw;
    width: auto;
  }
  .ad-btn {
    display: flex;
    justify-content: flex-start;
    flex-direction: column;
  }
  button.btnform {
    width: 100%;
    border: none;
    background: transparent;
  }
  .btnform p {
    text-align: center;
    font-size: var(--fs-pabtnform);
    font-weight: 700;
    padding: 1.1979166666666667vw 0;
    border-radius: 12vw;
    border: 0.13vw solid var(--co-pabtnform);
  }
  .bloquesucursales h2 {
    text-align: center;
    font-size: var(--fs-titsucu);
    margin-top: 7.552vw;
    margin-bottom: 2.864583333333333vw;
  }

  .imgpromomv {
    display: none;
  }
  .imgpromopc {
    display: block;
  }
  .bloquebtnubi {
    width: 30%;
    margin: auto;
  }
  .bloquebtnubi a p {
    font-size: var(--fs-txtbtnsu);
    line-height: 0.9427083333333334vw;
    width: 100%;
    margin: auto;
    border: 0.104vw solid #0017c5;
    padding: 2vw 0vw 2vw 0vw;
    border-radius: 7vw;
    margin-bottom: 6.822916666666666vw;
    cursor: pointer;
  }

  /***ajustes de carreta verde */
  .adjust {
    background-color: white;
  }

  .sectiontiktok {
    background: url("../assets/tiktokfondopc.png");
    background-size: cover;
    background-repeat: no-repeat;
    background-position-y: bottom;
    text-align: center;
    padding-bottom: 10vw;
  }
  .bloquetiktok {
    display: flex;
    justify-content: space-between;
    width: 87.135vw;
    margin: 0 auto 0 4.115vw;
  }
  .bloquetiktok h2 {
    color: var(--co-txttik);
    font-family: var(--font-titulo1);
    text-align: center;
    margin: 0;
    margin-top: 13.281vw;
    margin-bottom: 1.763285024154589vw;
  }
  .bloquetiktok img {
    width: 28.906vw;
    height: auto;
    margin-bottom: 1.83574879227053vw;
  }
  .bloquetiktok h6 {
    color: var(--co-txttik);
    font-family: var(--font-titulo1);
    font-size: var(--fs-txth5);
    width: 25.677vw;
    margin-top: 14.479vw !important;
    margin-bottom: 0;
    margin: auto;
  }
  .bloquebtntik p {
    /*color: var(--co-txtbtntik);*/
    color: var(--co-txtbtntikpc);
    font-family: var(--font-titulo1);
    font-size: 1.042vw;
    background: #005cb9;
    width: fit-content;
    padding: 1.198vw 3.448vw 1.198vw 4.648vw;
    border-radius: 30vw;
    margin: auto;
    margin-top: 1.771vw;
    margin-bottom: 0;
    line-height: 1.563vw;
    background-image: url("../assets/ttk2.svg");
    background-repeat: no-repeat;
    background-size: 1.094vw;
    background-position-y: 1.294vw;
    background-position-x: 2.865vw;
    transition: 0.5s;
  }
  .bloquebtntik p:hover {
    background: #ffa400;
    color: #005cb9;
    background-image: url("../assets/ttk.svg");
    background-repeat: no-repeat;
    background-size: 1.094vw;
    background-position-y: 1.294vw;
    background-position-x: 2.865vw;
  }
  .sectionformulario p.txt-ctc {
    font-size: 1.042vw;
    line-height: 111%;
    width: 100%;
    margin-bottom: 3.281vw;
    color: #F7E3DB;
  }
  .placa-v {
    position: absolute;
    margin-top: -14.271vw;
    right: 0;
    width: 11.823vw;
    display: block;
  }
  .sectionsucursales .matriz-cont {
    padding-top: 5.26vw;
  }
  .sectionsucursales .matriz-cont .tl {
    font-size: 3.802vw;
    font-family: var(--font-txtcon);
    line-height: 90.5%;
    font-weight: 700;
  }
  .sectionsucursales .matriz-cont p.subtl {
    font-size: 1.042vw;
    line-height: 115.5%;
    width: 34.115vw;
    margin: 4.583vw 0 6.406vw;
  }
  .sectionsucursales .matriz-cont .item {
    margin-bottom: 5.208vw;
  }
  .sectionsucursales .matriz-cont .item img {
    width: 5.208vw;
    height: 5.208vw;
    margin-bottom: 2.76vw;
  }
  .sectionsucursales .matriz-cont .item p,
  .sectionsucursales .matriz-cont .item a {
    font-size: 0.938vw;
    line-height: 111%;
    margin-bottom: 0;
  }
  .sectionsucursales .matriz-cont .threeitems {
    width: 53.854vw;
    display: flex;
    justify-content: space-between;
  }
  .sectionsucursales .matriz-cont .item.two {
    width: 20.677vw;
  }
  .sectionsucursales {
    padding-bottom: 0;
  }
}
</style>
