<template>
    <div class="politicas">
      <Navigator />
  
        <div class="banner">
            <p class="tit1">Aviso de privacidad</p>
  
        </div>
  
        <div class="contenido">
            <p class="txt1">
                Aviso de privacidad integral <br>
Bichaa Transportes mejor conocido como Bichaá, con domicilio en Avenida L #988 Colonia Ranchito Campestre, entre calle II y III. San Carlos nuevo guaymas y portal de internet www.bichaa.com, es el responsable del uso y protección de sus datos personales, y al respecto le informamos lo siguiente: <br>
¿Para qué fines utilizaremos sus datos personales?<br>
Los datos personales que recabamos de usted, los utilizaremos para las siguientes finalidades que son necesarias para el servicio que solicita:<br>
Respuesta a mensajes del formulario de contacto<br>
¿Qué datos personales utilizaremos para estos fines?<br>
Para llevar a cabo las finalidades descritas en el presente aviso de privacidad, utilizaremos los siguientes datos personales:<br>
Datos de identificación y contacto<br>


¿Cómo puede acceder, rectificar o cancelar sus datos personales, u oponerse a su uso o ejercer la revocación de consentimiento?<br>
Usted tiene derecho a conocer qué datos personales tenemos de usted, para qué los utilizamos y las condiciones del uso que les damos (Acceso). Asimismo, es su derecho solicitar la corrección de su información personal en caso de que esté desactualizada, sea inexacta o incompleta (Rectificación); que la eliminemos de nuestros registros o bases de datos cuando considere que la misma no está siendo utilizada adecuadamente (Cancelación); así como oponerse al uso de sus datos personales para fines específicos (Oposición). Estos derechos se conocen como derechos ARCO. <br>
Para el ejercicio de cualquiera de los derechos ARCO, debe enviar una petición vía correo electrónico a bichaamx@gmail.com y deberá contener:
<br>Nombre completo del titular.
<br>Domicilio.
<br>Teléfono.
<br>Correo electrónico usado en este sitio web.
<br>Copia de una identificación oficial adjunta.
<br>Asunto «Derechos ARCO»
<br><br>Descripción el objeto del escrito, los cuales pueden ser de manera enunciativa más no limitativa los siguientes: Revocación del consentimiento para tratar sus datos personales; y/o Notificación del uso indebido del tratamiento de sus datos personales; y/o Ejercitar sus Derechos ARCO, con una descripción clara y precisa de los datos a Acceder, Rectificar, Cancelar o bien, Oponerse. En caso de Rectificación de datos personales, deberá indicar la modificación exacta y anexar la documentación soporte; es importante en caso de revocación del consentimiento, que tenga en cuenta que no en todos los casos podremos atender su solicitud o concluir el uso de forma inmediata, ya que es posible que por alguna obligación legal requiramos seguir tratando sus datos personales. Asimismo, usted deberá considerar que para ciertos fines, la revocación de su consentimiento implicará que no le podamos seguir prestando el servicio que nos solicitó, o la conclusión de su relación con nosotros.
<br>¿En cuántos días le daremos respuesta a su solicitud?
<br>20 días
<br>d) ¿Por qué medio le comunicaremos la respuesta a su solicitud?
<br>bichaamx@gmail.com
<br><br>El uso de tecnologías de rastreo en nuestro portal de internet
<br>Le informamos que en nuestra página de internet utilizamos cookies, web beacons u otras tecnologías, a través de las cuales es posible monitorear su comportamiento como usuario de internet, así como brindarle un mejor servicio y experiencia al navegar en nuestra página. Los datos personales que obtenemos de estas tecnologías de rastreo son los siguientes:
<br>Idioma preferido por el usuario, Región en la que se encuentra el usuario, Tipo de navegador del usuario, Tipo de sistema operativo del usuario, Fecha y hora del inicio y final de una sesión de un usuario, Páginas web visitadas por un usuario, Búsquedas realizadas por un usuario, Publicidad revisada por un usuario
<br>Estas cookies, web beacons y otras tecnologías pueden ser deshabilitadas. Para conocer cómo hacerlo, consulte el menú de ayuda de su navegador. Tenga en cuenta que, en caso de desactivar las cookies, es posible que no pueda acceder a ciertas funciones personalizadas en nuestros sitio web.
<br><br>
¿Cómo puede conocer los cambios en este aviso de privacidad?
<br>El presente aviso de privacidad puede sufrir modificaciones, cambios o actualizaciones derivadas de nuevos requerimientos legales; de nuestras propias necesidades por los productos o servicios que ofrecemos; de nuestras prácticas de privacidad; de cambios en nuestro modelo de negocio, o por otras causas. Nos comprometemos a mantener actualizado este aviso de privacidad sobre los cambios que pueda sufrir y siempre podrá consultar las actualizaciones que existan en el sitio web www.bichaa.com.
             </p>
        </div>
        <Footer />
  
      </div>
  
  </template>
  <script>
  import { mapActions } from "vuex";
  import Navigator from "../components/Navigator";
  import Footer from "../components/Footer";
  
  export default{
    name: "Terms",
    components: {
      Navigator,
      Footer
    }
  
  }
  
  </script>
  
  <style scoped>
  
  .politicas{
  display: block;
  }
  
  .banner{
    display: block;
    width:100VW ;
    height:79.95169082125604VW ;
    background-image: url("../../src/assets/bckmb.png");
  
  }
  
  .tit1{
    display: block;
    color: #1E7E8B;
    padding-top: 47.82608695652174VW;
    padding-left: 14.391304347826086VW;
    padding-right: 14.391304347826086VW;
    font-size: 9.66183574879227VW;
    font-family: "Outfit";
    line-height: 13.285024154589372VW;
    text-align: center;
    margin: 0vw;
    font-weight: 700;
  }
  
  
  .contenido{
  
    display: block;
    padding-left: 8.937198067632849VW;
    padding-right: 8.937198067632849VW;
    padding-top: 14.975845410628018VW;
    padding-bottom: 14.975845410628018VW;
  
  }
  
  .txt1{
    display: block;
    font-size: 3.864734299516908VW;
    font-family: "Inter";
    color: #656565;
    line-height: 7.246376811594203VW;
    text-align: justify;
  
  }
  
  @media (min-width: 768px) {
    .politicas{
  display: block;
  }
  
  .banner{
    display: block;
    width:100VW ;
    height:23.020833333333332VW ;
    background-image: url("../../src/assets/bckpc.png");
  
  }
  
  .tit1{
    display: block;
    padding-top: 17.03125VW;
    padding-left: 22.03125VW;
    padding-right: 22.03125VW;
    font-size: 2.604166666666667VW;
    line-height: 3.619791666666667VW;
    text-align: center;
  }
  
  .contenido{
  
    display: block;
    padding-top: 4.114583333333333VW;
    padding-left: 16.09375VW;
    padding-right: 16.09375VW;
  
  }
  
  .txt1{
    display: block;
    font-size: 0.8333333333333334VW;
    line-height: 1.5625VW;
  
  
  }   
  }
  </style>