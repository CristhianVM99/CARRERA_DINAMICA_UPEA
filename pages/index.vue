<template>
  <div>

    <div class="menu_config" :style="{ left : menuPosition }" id="menu_config">
      <button @click="toggleMenu" class="close">
        <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="feather feather-settings"><circle cx="12" cy="12" r="3"></circle><path d="M19.4 15a1.65 1.65 0 0 0 .33 1.82l.06.06a2 2 0 0 1 0 2.83 2 2 0 0 1-2.83 0l-.06-.06a1.65 1.65 0 0 0-1.82-.33 1.65 1.65 0 0 0-1 1.51V21a2 2 0 0 1-2 2 2 2 0 0 1-2-2v-.09A1.65 1.65 0 0 0 9 19.4a1.65 1.65 0 0 0-1.82.33l-.06.06a2 2 0 0 1-2.83 0 2 2 0 0 1 0-2.83l.06-.06a1.65 1.65 0 0 0 .33-1.82 1.65 1.65 0 0 0-1.51-1H3a2 2 0 0 1-2-2 2 2 0 0 1 2-2h.09A1.65 1.65 0 0 0 4.6 9a1.65 1.65 0 0 0-.33-1.82l-.06-.06a2 2 0 0 1 0-2.83 2 2 0 0 1 2.83 0l.06.06a1.65 1.65 0 0 0 1.82.33H9a1.65 1.65 0 0 0 1-1.51V3a2 2 0 0 1 2-2 2 2 0 0 1 2 2v.09a1.65 1.65 0 0 0 1 1.51 1.65 1.65 0 0 0 1.82-.33l.06-.06a2 2 0 0 1 2.83 0 2 2 0 0 1 0 2.83l-.06.06a1.65 1.65 0 0 0-.33 1.82V9a1.65 1.65 0 0 0 1.51 1H21a2 2 0 0 1 2 2 2 2 0 0 1-2 2h-.09a1.65 1.65 0 0 0-1.51 1z"></path></svg>
      </button>
      <div class="notificationCard">
        <p class="notificationHeading">{{ carrera_nombre }}</p>
        <!--<img style="width: 100px;" :src="url_api + '/InstitucionUpea/' + institucion_logo" alt="">-->
        <p class="notificationPara">Configuracion de la Pagina</p>
        <div class="buttonContainer">
          <!-- index -->
          <!-- <button @click="cambiarIndex(1)" class="AllowBtn">Index 1</button> -->
          <!--<button @click="cambiarIndex(2)" class="AllowBtn">Index 2</button>
          <button @click="cambiarIndex(3)" class="AllowBtn">Index 3</button>
          <button @click="cambiarIndex(5)" class="AllowBtn">Index 5</button>
          <button @click="cambiarIndex(7)" class="AllowBtn">Index 7</button>
          <button @click="cambiarIndex(8)" class="AllowBtn">Index 8</button>-->

          <!-- autoridades -->
          <button @click="toggleAutoridades1" :class="mostrarAutoridades1 ? 'AllowBtn': 'NotnowBtn'">Autoridades 1</button>
          <button @click="toggleAutoridades2" :class="mostrarAutoridades2 ? 'AllowBtn': 'NotnowBtn'">Autoridades  2</button>

          <!-- videos  -->
          <button @click="toggleVideo1" :class="mostrarVideo1 ? 'AllowBtn': 'NotnowBtn'">Video 1</button>
          <button @click="toggleVideo2" :class="mostrarVideo2 ? 'AllowBtn': 'NotnowBtn'">Video 2</button>

          <!-- convocatorias -->
          <button @click="toggleConvocatorias1" :class="mostrarConvocatorias1 ? 'AllowBtn': 'NotnowBtn'">Convocatorias 1</button>
          <button @click="toggleConvocatorias2" :class="mostrarConvocatorias2 ? 'AllowBtn': 'NotnowBtn'">Convocatorias 2</button>
          <button @click="toggleConvocatorias3" :class="mostrarConvocatorias3 ? 'AllowBtn': 'NotnowBtn'">Convocatorias 3</button>
          
          <!-- cursos -->
          <button @click="toggleCursos1" :class="mostrarCursos1 ? 'AllowBtn': 'NotnowBtn'">Cursos 1</button>
          <button @click="toggleCursos2" :class="mostrarCursos2 ? 'AllowBtn': 'NotnowBtn'">Cursos 2</button>
          <button @click="toggleCursos3" :class="mostrarCursos3 ? 'AllowBtn': 'NotnowBtn'">Cursos 3</button>

          <!-- enlaces -->
          <button @click="toggleEnlaces1" :class="mostrarEnlaces1 ? 'AllowBtn': 'NotnowBtn'">Enlaces 1</button>
          <button @click="toggleEnlaces2" :class="mostrarEnlaces2 ? 'AllowBtn': 'NotnowBtn'">Enlaces 2</button>
        </div>
      </div>
    </div>
    <!-- ======================== NAVBAR ====================== -->

    <!-- 1 -->      <Navbar           ref="navbar"        lr="logoRef"   v-if="(index==1)"/>
    <!-- 2 -->      <Navbar           ref="navbar"        theme="light"  v-if="(index==2)"/>
    <!-- 3 -->      <Navbar           ref="navbar"        theme="light"  v-if="(index==3)"/>
    <!-- 5 -->      <Navbar           ref="navbar"        theme="light"  v-if="(index==5)"/>
    <!-- 7 -->      <Navbar           ref="navbar"        theme="light"  v-if="(index==7)"/>
    <!-- 8 -->      <NavbarArch       ref="navbar"                       v-if="(index==8)"/>

    <!-- ======================== BANNER ======================= -->

    <!-- 1 -->      <IntroWithSlider  ref="fixedSlider"                  v-if="(index==1)"/>
    <!-- 2 -->      <Intro2                                              v-if="(index==2)"/>
    <!-- 3 -->      <Intro3                                              v-if="(index==3)"/>
    <!-- 5 -->      <Intro4                               theme="light"  v-if="(index==5)"/>
    <!-- 6 -->      <IntroWithSlider  ref="fixedSlider"                  v-if="(index==6)"/>
    <!-- 7 -->      <FreelancreIntro                                     v-if="(index==7)"/>
    <!-- 8 -->      <Intro5                                              v-if="(index==8)"/>

    <!-- ======================== CONTENT ====================== -->
    <div class="main-content" ref="MainContent">              
      
      <!-- Autoridades -->
      <Blogs1 v-if="mostrarAutoridades1" tipo="autoridades"/>      
      <Blogs3 v-if="mostrarAutoridades2" tipo="autoridades"/>          

      <!-- seccion del video de la carrera-->
      <VideoWithTestimonials v-if="mostrarVideo1"/>
      <div style="height: 50px;"  v-if="mostrarVideo1"></div>
      <Video v-if="mostrarVideo2"/>            
      
      <!-- organigrama carrera -->
      <CallToAction v-if="true"/>        

      <!-- fotos intermedio -->
      <div v-if="foto != null && Object.keys(foto).length != 0" :style="`background-image: url(${url_api + '/InstitucionUpea/Portada/' + foto.portada_imagen});`" class="intermedio"></div>
      <div v-else class="intermedio"></div>


      <!-- CONVOCATORIAS -->
      <Blogs1 v-if="mostrarConvocatorias1" tipo="convocatorias" />      
      <Blogs2 v-if="mostrarConvocatorias2" tipo="convocatorias"/>      
      <Blogs3 v-if="mostrarConvocatorias3" tipo="convocatorias"/>       

      <!-- fotos intermedio -->
      <div v-if="foto != null && Object.keys(foto).length != 0" :style="`background-image: url(${url_api + '/InstitucionUpea/Portada/' + foto.portada_imagen});`" class="intermedio"></div>
      <div v-else class="intermedio"></div>

      <!-- CURSOS -->
      <Blogs1 v-if="mostrarCursos1" tipo="cursos" /> 
      <Blogs2 v-if="mostrarCursos2" tipo="cursos"/>
      <Blogs3 v-if="mostrarCursos3" tipo="cursos"/>  
      
      <!-- enlace de paginas web -->
      <Clients1 v-if="mostrarEnlaces1" theme="light" />
      <Clients2 v-if="mostrarEnlaces2" theme="light" :length="Object.keys(carrera_links).length" />     
      
      <!-- ================================== COMPONENTES POR VER ==========================-->
      <!--<Services1 />
      <Services1 oStyle="4item" />      
      <Services1 lines />
      <Services2 />
      <Services3 />
      <Services4 serviceMB50 />
      <Services5 />
      <Services6 />-->

      <!-- about's -->
      <!--<AboutUs1 />
      <AboutUs2 />
      <AboutUs3 />
      <AboutUs4 />
      <AboutUs5 />
      <AboutUs6 />-->    

      <!-- <Blogs4 v-if="false"/>

      <Portfolio v-if="false" :grid="3" filterPosition="center" />
      <Portfolio v-if="false" grid="2" filterPosition="left" />
      
      <FullTestimonials v-if="false" noPadding />
      <FullTestimonials v-if="false" withCOLOR />
      <FullTestimonials v-if="false" classText="pb-0" />
      <FullTestimonials v-if="false" />
      <FullTestimonials v-if="false" showHead />

      <TestimonialsArcho v-if="false"/>

      <Team1 v-if="false" />
      <Team2 v-if="false" theme="light" />
      <Team3 v-if="false" />

      <CallToAction v-if="false" img="/img/patrn1.png" />

      <Works1 v-if="false" />
      <Works2 v-if="false" />
      <Works3 v-if="false" />
      <Works4 v-if="false" classText="blackFilterColor" />
      <Works5 v-if="false" />
      <Works6 v-if="false" />

      <FunFacts1 v-if="false"/> 
      <FunFacts2 v-if="false"/>   

      <SkillsCircle v-if="false" theme="light" />

      <SContactForm v-if="false" />
      <SContactForm v-if="false" noLine />

      <MinimalArea2 v-if="false"/>

      <CaseStudy v-if="false"/>

      <LatestNews v-if="false"/>
      <ContactArcho v-if="false"/>
       -->
      <Footer />
      <!-- <Footer v-if="false" hideBGCOLOR />-->
      <!-- <FooterArch v-if="true"/>  -->
    </div>

  </div>
</template>

<script>

/* importacion del store de manera global desde pinia */
import { useInstitucionStore } from '@/store/store'

export default {
  layout: "light",
  async asyncData({ $axios }) {        
        try {            
            const useInstitucion = useInstitucionStore()     
            const institucion = await $axios.$get('/api/InstitucionUPEA/' + process.env.APP_ID_INSTITUCION)
            const carrera_links_externos = await $axios.$get('/api/linksIntExtAll/' + process.env.APP_ID_INSTITUCION)
            const ComunicadosFilter = await $axios.$get('/api/convocatoriasAll/' + process.env.APP_ID_CARRERA)
            const CursosFilter = await $axios.$get('/api/cursosAll/' + process.env.APP_ID_CARRERA)
            const carrera_servicios = await $axios.$get('/api/ServicioAll/' + process.env.APP_ID_CARRERA)
            const carrera_ofertasacademicas = await $axios.$get('/api/OfertasAcademicasAll/' + process.env.APP_ID_CARRERA)
            const carrera_publicaciones = await $axios.$get('/api/publicacionesAll/' + process.env.APP_ID_INSTITUCION)
            const carrera_gacetas = await $axios.$get('/api/gacetaunivAll/' + process.env.APP_ID_INSTITUCION)
            const carrera_eventos = await $axios.$get('/api/eventoAll/' + process.env.APP_ID_INSTITUCION)
            const carrera_videos = await $axios.$get('/api/VideosAll/' + process.env.APP_ID_INSTITUCION)

            let fotosPagina = institucion.Descripcion.portada.filter(port => port.portada_titulo === "PAGINA")
            let fotosPortada = institucion.Descripcion.portada.filter(port => port.portada_titulo != "PAGINA")
            let carrera_ConvocatoriasAll = ComunicadosFilter.filter(conv => conv.tipo_conv_comun.tipo_conv_comun_estado === "1") 
            let carrera_CursosAll = CursosFilter.filter(cur => cur.det_estado === '1')
            
            let comunicados = carrera_ConvocatoriasAll.filter(conv => conv.tipo_conv_comun.tipo_conv_comun_titulo === "COMUNICADOS")
            let convocatorias = carrera_ConvocatoriasAll.filter(conv => conv.tipo_conv_comun.tipo_conv_comun_titulo === "CONVOCATORIAS")
            let avisos = carrera_ConvocatoriasAll.filter(conv => conv.tipo_conv_comun.tipo_conv_comun_titulo === "AVISOS")            
            let cursos = carrera_CursosAll.filter(cur => cur.tipo_curso_otro.tipo_conv_curso_nombre === "CURSOS")
            let seminarios = carrera_CursosAll.filter(cur => cur.tipo_curso_otro.tipo_conv_curso_nombre === "SEMINARIOS")

            useInstitucion.asignarCarreraLinksExternos(carrera_links_externos)
            useInstitucion.asignarInstitucion(institucion.Descripcion)
            useInstitucion.asignarConvocatorias(convocatorias)
            useInstitucion.asignarComunicados(comunicados)
            useInstitucion.asignarAvisos(avisos)
            useInstitucion.asignarCursos(cursos)
            useInstitucion.asignarSeminarios(seminarios)
            useInstitucion.asignarServicios(carrera_servicios)
            useInstitucion.asignarOfertasAcademicas(carrera_ofertasacademicas)
            useInstitucion.asignarPublicaciones(carrera_publicaciones)
            useInstitucion.asignarGacetas(carrera_gacetas)
            useInstitucion.asignarEventos(carrera_eventos)
            useInstitucion.asignarVideos(carrera_videos)
            useInstitucion.asignarFotosPagina(fotosPagina)
            useInstitucion.asignarFotosPortada(fotosPortada)            
        } catch (e) {
            console.error("error",e)
        }
  },
  data() {
    return {
      carrera_nombre : useInstitucionStore().institucion.institucion_nombre,
      institucion_logo : useInstitucionStore().institucion.institucion_logo,
      url_api : process.env.APP_ROOT_API,
      carrera_colores : useInstitucionStore().institucion.colorinstitucion,
      foto: useInstitucionStore().fotosPagina[2],
      carrera_links: useInstitucionStore().carrera_links_externos,
      index: 8,      

      menuPosition: '-220px',
      isMenuOpen: false,

      /* variables para saber que mostrar */
      mostrarAutoridades1: true,
      mostrarAutoridades2: false,
      mostrarVideo1: true,
      mostrarVideo2: false,
      mostrarConvocatorias1: true,
      mostrarConvocatorias2: false,
      mostrarConvocatorias3: false,
      mostrarCursos1: true,
      mostrarCursos2: false,
      mostrarCursos3: false,
      mostrarEnlaces1: true,
      mostrarEnlaces2: false,
    }
  },
  head() {
    return {
      title: 'UPEA | '+this.carrera_nombre,
      link: [
        { rel: 'icon', type:"image/x-icon", href: this.url_api + '/InstitucionUpea/' + this.institucion_logo }
      ]
    }
  }, 
  methods: {    
    toggleAutoridades1() {
      this.mostrarAutoridades1 = !this.mostrarAutoridades1;
    },
    toggleAutoridades2() {
      this.mostrarAutoridades2 = !this.mostrarAutoridades2;
    },
    toggleVideo1() {
      this.mostrarVideo1 = !this.mostrarVideo1;
    },
    toggleVideo2() {
      this.mostrarVideo2 = !this.mostrarVideo2;
    },
    toggleConvocatorias1() {
      this.mostrarConvocatorias1 = !this.mostrarConvocatorias1;
    },
    toggleConvocatorias2() {
      this.mostrarConvocatorias2 = !this.mostrarConvocatorias2;
    },
    toggleConvocatorias3() {
      this.mostrarConvocatorias3 = !this.mostrarConvocatorias3;
    },
    toggleCursos1() {
      this.mostrarCursos1 = !this.mostrarCursos1;
    },
    toggleCursos2() {
      this.mostrarCursos2 = !this.mostrarCursos2;
    },
    toggleCursos3() {
      this.mostrarCursos3 = !this.mostrarCursos3;
    },
    toggleEnlaces1() {
      this.mostrarEnlaces1 = !this.mostrarEnlaces1;
    },
    toggleEnlaces2() {
      this.mostrarEnlaces2 = !this.mostrarEnlaces2;
    },
    toggleMenu() {
      this.isMenuOpen = !this.isMenuOpen;
      this.menuPosition = this.isMenuOpen ? '0' : '-220px';
    },    
    index1(){
      if (this.$refs.fixedSlider.$el && this.$refs.MainContent) {
      var slidHeight = this.$refs.fixedSlider.$el.offsetHeight;      
        this.$refs.MainContent.style.marginTop = slidHeight + "px";
      }
      var navbar = this.$refs.navbar.$el,
        logo = this.$refs.navbar.$refs.lr;
      if (window.pageYOffset > 300) {
        navbar.classList.add("nav-scroll");
      } else {
        navbar.classList.remove("nav-scroll");
      }
      window.addEventListener("scroll", () => {
        if (window.pageYOffset > 300) {
          navbar.classList.add("nav-scroll");
          //logo.setAttribute("src", "/img/logo-dark.png");
        } else {
          navbar.classList.remove("nav-scroll");
          //logo.setAttribute("src", "/img/logo-light.png");
        }
      });
    },

    index2(){
      var navbar = this.$refs.navbar.$el;
      if (window.pageYOffset > 300) {
        navbar.classList.add("nav-scroll");
      } else {
        navbar.classList.remove("nav-scroll");
      }
      window.addEventListener("scroll", () => {
        if (window.pageYOffset > 300) {
          navbar.classList.add("nav-scroll");
        } else {
          navbar.classList.remove("nav-scroll");
        }
      });
    },

    index3(){
      var navbar = this.$refs.navbar.$el;
      if (window.pageYOffset > 300) {
        navbar.classList.add("nav-scroll");
      } else {
        navbar.classList.remove("nav-scroll");
      }
      window.addEventListener("scroll", () => {
        if (window.pageYOffset > 300) {
          navbar.classList.add("nav-scroll");
        } else {
          navbar.classList.remove("nav-scroll");
        }
      });
    },

    index4(){
      if (this.$refs.fixedSlider.$el && this.$refs.MainContent) {
        var slidHeight = this.$refs.fixedSlider.$el.offsetHeight;
        this.$refs.MainContent.style.marginTop = slidHeight + "px";
      }
      var navbar = this.$refs.navbar.$el,
        logo = this.$refs.navbar.$refs.lr;
      if (window.pageYOffset > 300) {
        navbar.classList.add("nav-scroll");
      } else {
        navbar.classList.remove("nav-scroll");
      }
      window.addEventListener("scroll", () => {
        if (window.pageYOffset > 300) {
          navbar.classList.add("nav-scroll");
          //logo.setAttribute("src", "/img/logo-dark.png");
        } else {
          navbar.classList.remove("nav-scroll");
          //logo.setAttribute("src", "/img/logo-light.png");
        }
      });
    },

    index5(){
      var navbar = this.$refs.navbar.$el;
      if (window.pageYOffset > 300) {
        navbar.classList.add("nav-scroll");
      } else {
        navbar.classList.remove("nav-scroll");
      }
      window.addEventListener("scroll", () => {
        if (window.pageYOffset > 300) {
          navbar.classList.add("nav-scroll");
        } else {
          navbar.classList.remove("nav-scroll");
        }
      });
    },

    index6(){
      if (this.$refs.fixedSlider.$el && this.$refs.MainContent) {
        var slidHeight = this.$refs.fixedSlider.$el.offsetHeight;
        this.$refs.MainContent.style.marginTop = slidHeight + "px";
      }
      var navbar = this.$refs.navbar.$el,
        logo = this.$refs.navbar.$refs.lr;
      if (window.pageYOffset > 300) {
        navbar.classList.add("nav-scroll");
      } else {
        navbar.classList.remove("nav-scroll");
      }
      window.addEventListener("scroll", () => {
        if (window.pageYOffset > 300) {
          navbar.classList.add("nav-scroll");
          //logo.setAttribute("src", "/img/logo-dark.png");
        } else {
          navbar.classList.remove("nav-scroll");
          //logo.setAttribute("src", "/img/logo-light.png");
        }
      });
    },

    index7(){
      var navbar = this.$refs.navbar.$el;
      if (window.pageYOffset > 300) {
        navbar.classList.add("nav-scroll");
      } else {
        navbar.classList.remove("nav-scroll");
      }
      window.addEventListener("scroll", () => {
        if (window.pageYOffset > 300) {
          navbar.classList.add("nav-scroll");
        } else {
          navbar.classList.remove("nav-scroll");
        }
      });
    },

    index8(){
      var navbar = this.$refs.navbar.$el,
        logo = this.$refs.navbar.$refs.lr;
      if (window.pageYOffset > 300) {
        navbar.classList.add("nav-scroll");
      } else {
        navbar.classList.remove("nav-scroll");
      }
      window.addEventListener("scroll", () => {
        if (window.pageYOffset > 300) {
            //logo.setAttribute("src", "/img/logo-dark.png");
          navbar.classList.add("nav-scroll");
        } else {
            //logo.setAttribute("src", "/img/logo-light.png");
          navbar.classList.remove("nav-scroll");
        }
      });
    },

    cambiarIndex(index) {
      this.index = index;                
    },

    setColor(){
      if (Object.keys(this.carrera_colores).length != 0) {
      if (process.client) { // Verifica si el código se está ejecutando en el lado del cliente
        document.documentElement.style.setProperty(
          '--color-primario',
          this.carrera_colores[0].color_primario
        );
        document.documentElement.style.setProperty(
          '--color-secundario',
          this.carrera_colores[0].color_primario
        );
        document.documentElement.style.setProperty(
          '--color-terciario',
          this.carrera_colores[0].color_secundario
        );
      }
      }
    },  

    createdComponent(){
      this.setColor()
    },
  },
  created() {   
    this.createdComponent()
  },
  mounted() {
    switch (this.index) {
      case 1:
        this.index1()
        break;

      case 2:
        this.index2()
        break;

      case 3:
        this.index3()
        break;

      case 4:
        this.index4()
        break;

      case 5:
        this.index5()
        break;

      case 6:
        this.index6()
        break;

      case 7:
        this.index7()
        break;
      
      case 8:
        this.index8()
        break;

      default:
        break;
      }  
  },

  beforeDestroy() {
    window.removeEventListener('scroll', this.handleScroll); // Limpia el evento de desplazamiento antes de destruir el componente
  }
};
</script>

<style scoped>
.intermedio{
  height: 300px;
  background-image: url(/img/universidad/intermedio.jpg);
  background-repeat: none;
  background-size: cover;
  background-attachment: fixed;
}
.menu_config{
  position: fixed;
  top: 50%;
  z-index: 1000;
  transform: translateY(-50%);
}
.notificationCard {
  width: 220px;
  background: rgb(245, 245, 245);
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  padding: 20px 35px;
  gap: 10px;
  box-shadow: 5px 5px 10px rgba(0, 0, 0, 0.123);
  
}

.bellIcon {
  width: 50px;
  margin: 20px 0px;
}

.bellIcon path {
  fill: rgb(168, 131, 255);
}

.notificationHeading {
  color: black;
  font-weight: 600;
  font-size: 0.8em;
}

.notificationPara {
  color: rgb(133, 133, 133);
  font-size: 0.6em;
  font-weight: 600;
  text-align: center;
}

.buttonContainer {
  display: flex;
  flex-direction: column;
}

.AllowBtn {
  width: 120px;
  height: 25px;
  background-color: rgb(168, 131, 255);
  color: white;
  border: none;
  border-radius: 20px;
  font-size: 0.7em;
  font-weight: 600;
  cursor: pointer;
}

.NotnowBtn {
  width: 120px;
  height: 25px;
  color: rgb(168, 131, 255);
  border: none;
  background-color: transparent;
  font-weight: 600;
  font-size: 0.7em;
  cursor: pointer;
  border-radius: 20px;
}

.NotnowBtn:hover {
  background-color: rgb(239, 227, 255);
}

.AllowBtn:hover {
  background-color: rgb(153, 110, 255);
}

.close {
  background: rgb(245, 245, 245);
  border-top-right-radius: 20px;
  border-bottom-right-radius: 20px;
  width: 40px;
  height: 40px;
  padding-bottom: none;
  outline: none;
}
</style>