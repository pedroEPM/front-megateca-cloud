<template>

  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin="">
  <link href="https://fonts.googleapis.com/css2?family=Anton&family=Great+Vibes&family=Lora:ital,wght@0,400..700;1,400..700&family=Oswald&family=Roboto:ital,wght@0,100;0,300;0,400;0,500;0,700;0,900;1,100;1,300;1,400;1,500;1,700;1,900&display=swap" rel="stylesheet">

  <footer class="footer">
      <div class="social-media">
        <img src="@/public/facebook.png" alt="Facebook"/>
        <img src="@/public/twitter.png" alt="Twitter"/>
        <img src="@/public/instagram.png" alt="Instagram"/>
        <img src="@/public/youtube.png" alt="YouTube"/>
      </div>

      <div class="logo">
        <img src="@/public/logoDiario.png" alt="Diario de Yucatán">
      </div>

      <div class="navigation">
        <button @click="login" style="color: black; font-weight: bold;">Iniciar Sesión</button>
        <button @click="subscribe" style="background-color: #0C5873;color: white;">Suscríbete</button>
        <button @click="search" class="search-button">
          <img src="../public/búsqueda.png" alt="Buscar">
        </button>
      </div>
    </footer>

  <div class="sub-menu">
      <ul>
        <li><a href="/merida">MÉRIDA</a></li>
        <li><a href="/yucatan">YUCATÁN</a></li>
        <li class="dropdown">
          <a href="/mexico">MÉXICO ▼</a>
          <div class="dropdown-content">
            <a href="/campeche">Campeche</a>
            <a href="/quintanaroo">Quintana Roo</a>
          </div>
        </li>
        <li><a href="/mundo">MUNDO</a></li>
        <li><a href="/economia">ECONOMÍA</a></li>
        <li><a href="/editorial">EDITORIAL</a></li>
        <li><a href="/tecnologia">TECNOLOGÍA</a></li>
        <li><a href="/deportes">DEPORTES</a></li>
        <li><a href="/espectaculos">ESPECTÁCULOS</a></li>
        <li class="dropdown">
          <a href="/imagen">IMAGEN ▼</a>
          <div class="dropdown-content">
            <a href="/campeche">Semana hace 50 años</a>
          </div>
        </li>
        <li><a href="/central9">CENTRAL 9</a></li>
        <li class="dropdown">
          <a href="/mas">MÁS ▼</a>
          <div class="dropdown-content">
            <a href="/obituarios">Obituarios</a>
            <a href="/sociales">Sociales</a>
            <a href="/avisoseconomicos">Avisos Economicos</a>
            <a href="/sumplementos">Sumplementos</a>
            <a href="/contacto">Contacto</a>
          </div>
        </li>
      </ul>
    </div>

    <div class="search-container">
      <div class="input-group">
        <span class="input-icon">
          <img src="../public/búsqueda.png" alt="Buscar"/>
        </span>
        <input type="text" placeholder="Buscar" v-model="searchQuery">
      </div>
      <button class="button-date" @click="searchByText">Buscar</button>
    </div>

  <div class="time-machine">
    <h1 class="main-title">Tal día como hoy</h1>
  </div>

 <p v-if="dialog">Getting data</p>
  <v-container>
    <v-row v-if="pdfs.length > 0">
      <v-col
        v-for="item in pdfs"
        :key="item._id"
        cols="12"
        sm="12"
        md="3"
      >
        <cCardVue
          :notebook="item.notebook[0]?.NoteBookName ?? 'Sin cuaderno'"
          :publication="item.publication[0]?.publicationName ?? 'Sin publicación'"
          :date="item.datePublication"
          :image="storage + item.newSRCPDFThumbnail"
          :newId="item.isNewId"
        />
      </v-col>
    </v-row>
  </v-container>

  <div class="pagination-buttons">
    <button class="button-date" @click="prevPage" :disabled="page === 1">Página Anterior</button>
    <button class="button-date" @click="nextPage">Siguiente Página</button>
      <p id="currentPage">{{ page }}</p>

  </div>


  <footer class="footer-container">
      <div class="footer-links">
        <img src="@/public/footer-mega-media.png" alt="Grupo Megamedia" class="footer-logo" style="width: 180px; height: auto;">
        <a href="/sociales"><img src="@/public/footer-logo-sociales.png" alt="Sociales" class="link-icon" style="width: 70px; height: 10px;"></a>
        <a href="/planb"><img src="@/public/footer-logo-9.png" alt="Plan B" class="link-icon" style="width: auto; height: auto;"></a>
        <a href="/avisoseconomicos"><img src="@/public/footer-logo-2-1.png" alt="Avisos Económicos" class="link-icon" style="width: auto; height: auto;"></a>
        <a href="/cmujer"><img src="@/public/footer-logo-3-1.png" alt="C Mujer" class="link-icon" style="width: auto; height: auto;"></a>
        <a href="/descubro"><img src="@/public/footer-logo-4.png" alt="Descubro" class="link-icon" style="width: auto; height: auto;"></a>
        <a href="/meganews"><img src="@/public/footer-logo-5.png" alt="Mega News" class="link-icon" style="width: auto; height: auto;"></a>
        <a href="/empleate"><img src="@/public/footer-logo-8-2.png" alt="Empléate" class="link-icon" style="width: auto; height: auto;"></a>
        <a href="/megashop"><img src="@/public/footer-logo-7.png" alt="Mega Shop" class="link-icon" style="width: auto; height: auto;"></a>
        <a href="/alchile"><img src="@/public/footer-logo-1-1.png" alt="Al Chile" class="link-icon" style="width: auto; height: auto;"></a>
      </div>
  </footer>

  <footer class="footer-container2">

      <div class="footer-bottom">
        <p>Prohibida su reproducción total o parcial, así como su traducción a cualquier idioma sin autorización escrita de su titular.</p>
        <p>© 2024 Derechos Reservados Diario Yucatán.</p>
        <p>Powered by DimitriMedNov</p>
      </div>

      <div class="social-links">
        <a href="http://facebook.com"><img src="@/public/facebookblanco.png" alt="Facebook"></a>
        <a href="http://twitter.com"><img src="@/public/twitterblanco.png" alt="Twitter"></a>
        <a href="http://instagram.com"><img src="@/public/instagramblanco.png" alt="Instagram"></a>
      </div>

    </footer>

</template>


<script>
import cCardVue from '~/components/cCard.vue';

export default {
  components: {
    cCardVue
  },
  data() {
    return {
      dialog: true,
      api: useRuntimeConfig().public.apiBase,
      storage: useRuntimeConfig().public.storage,
      pdfs: [],
      page: 1,
      searchQuery: ''
    };
  },
  methods: {
    async getPDFs() {
      try {
        this.dialog = true;
        const response = await $fetch(`${this.api}/pdfs?page=${this.page}`, {
          method: 'GET',
        });
        this.pdfs = response?.msg || [];
        this.dialog = false;
      } catch (error) {
        console.log('Error ', error);
        this.dialog = false;
      }
    },
    async searchByText() {
      try {
        this.dialog = true;
        const response = await $fetch(`${this.api}/search?query=${this.searchQuery}`, {
          method: 'GET',
        });
        this.pdfs = response?.msg || [];
        this.dialog = false;
      } catch (error) {
        console.log('Error ', error);
        this.dialog = false;
      }
    },
    async nextPage() {
      this.page += 1;
      await this.getPDFs();
      document.getElementById('currentPage').innerText = this.page;
    },
    async prevPage() {
      if (this.page > 1) {
        this.page -= 1;
        await this.getPDFs();
        document.getElementById('currentPage').innerText = this.page;
      }
    }
  },
  mounted() {
    this.getPDFs();
  }
};
</script>

<style scoped>

.pagination-buttons {
  display: flex;
  justify-content: center;
  gap: 10px;
  margin-top: 20px;
}

.footer-container {
  background-color: #202931;
  display: flex;
  align-items: center;
  flex-direction: column;
}

.footer-links {
  display: flex;
  margin: 20px 0;
}

.footer-container2 {
  background-color: #202931;
  color: #ccc;
  padding: 10px;
  display: flex;
  justify-content: flex-end;
}

.footer-links a {
  margin: 0 15px;
  display: flex;
  align-items: center;
}

.footer-bottom {
  text-align: left;
  font-size: 16px;
  width: 100%;
  border-top: 1px solid #444;
  padding-top: 10px;
}

.social-links {
  display: flex;
  justify-content: center;
  padding: 10px 0;
}

.social-links a {
  margin: 0 10px;
}

.social-links img {
  width: 30px;
  height: 30px;
}

.sub-menu {
  position: fixed;
  top: 60px;
  height: 40px;
  left: 0;
  z-index: 1001;
  background-color: white;
  margin-top: 40px;

  display: flex;
  justify-content: center;
  align-items: center;
  width: 100%;
  border-top: 1px solid #ccc;
  border-bottom: 1px solid #ccc;
}

.sub-menu ul {
  display: flex;
  list-style: none;
  margin: 0;

  width: 100%;
  justify-content: center;
}

.sub-menu li {
  margin: 0 15px;
  white-space: nowrap;
}

.sub-menu a {
  color: black;
  text-decoration: none;
  font-weight: bold;
  font-size: 14px;
  font-family: "Lora", serif;
  padding: 10px 5px;
}

.sub-menu a:hover {
    background-color: #EBEBEB;
}

.dropdown {
  position: relative;
  display: inline-block;
}

.dropdown-content {
  display: none;
  position: absolute;
  background-color: #f9f9f9;
  min-width: 160px;
  box-shadow: 0px 8px 16px 0px rgba(0,0,0,0.2);
  z-index: 1;
  left: 0;
}

.dropdown-content a {
  color: black;
  padding: 12px 16px;
  text-decoration: none;
  display: block;
  text-align: left;
}

.dropdown:hover .dropdown-content {
  display: block;
}

.time-machine {
  display: flex;
  flex-direction: column;
  align-items: flex-start;;
  width: 100%;
}

.main-title {
  text-align: left;
  padding-left: 80px;
  margin-top: 20px;
  font-size: 24px;
  font-weight: bold;
  font-family: "Lora", serif;
  color: #333333;
}

.newspapers {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  gap: 20px;
  padding: 20px;
}

.newspaper {
  flex-basis: 20%;
  box-shadow: 0 4px 8px rgba(0,0,0,0.1);
  margin: 10px;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.newspaper img {
  width: 100%;
  height: auto;
  margin-bottom: 10px;
}

.newspaper h2, .newspaper p {
  text-align: left;
  margin: 5px 0;
}

.date-box {
  font-family: "Lora", serif;
  border-radius: 5px;
  padding: 10px;
  width: 100%;
  margin-top: 0;
  padding-top: 5px;
}

.date {
  text-align: left;
  margin: 0;
  color: #333333;
}

.date-sub {
  text-align: left;
  font-weight: bold;
  margin: 0;
  font-size: 0.9em;
  color: #4F92C9;
}

.link {
  background: #001c4c;
  color: white;
  padding: 10px 20px;
  width: 80%;
  margin-top: 20px;
  text-decoration: none;
  border-radius: 20px;
  transition: background-color 0.3s, box-shadow 0.3s;
  font-family: "Anton", sans-serif;
  font-weight: 100;
  font-style: normal;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.2);
  cursor: pointer;
  margin-bottom: 10px;
}

.link:hover {
  background: #4F89B9;
}

.footer {
  margin-top: 20px;
  background-color: #FFFFFF;
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: 100%;
  position: fixed;
  top: 0;
  left: 0;
  z-index: 1000;
  padding: 0 20px;
  height: 60px;
}

.footer .social-media,
.footer .navigation {
  flex: 1;
  display: flex;
  justify-content: center;
}

.footer .navigation {
  display: flex;
  align-items: center;
  justify-content: flex-end;
  width: 100%;
  margin: 0 auto;
}

.footer .logo {
  flex: 0;
}

.footer .social-media {
  margin-right: auto;
  margin-left: 5%;
}

.footer .navigation {
  margin-left: auto;
  margin-right: 5%;
}

.footer button {
  margin-right: 10px;
}

.footer button:last-child {
  margin-right: 0;
}

.social-media img {
  margin: 0 5px;
  width: 23px;
  height: 23px;
}

.logo {
  margin: 0 auto;
  text-align: center;
}

.logo img {
  width: 450px;
  height: 70px;
}

.navigation {
  display: flex;
  align-items: center;
}

.navigation button {
  font-size: medium;
  color: white;
  border-radius: 5px;
  padding: 10px 20px;
  cursor: pointer;
}

.button .search-button {
  border: none;
  border-radius: 5px;
  padding: 10px 20px;
  margin-right: 10px;
  cursor: pointer;
  font-size: 16px;
}

.search-button {
  width: 40px;
  padding: 10px;
  display: flex;
  justify-content: center;
  align-items: center;
}

.search-button img {
  width: 30px;
  height: auto;
}

.search-container {
  font-family: "Lora", serif;
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 10px;
  top: 120px;
  left: 0;
  right: 0;
  width: 100%;
  z-index: 1002;
  margin-top: 90px;
  margin-bottom: 10px;
  gap: 5px;
}

.input-group, .date-group {
  display: flex;
  align-items: center;
  background: #fff;
  border-radius: 20px;
  padding: 5px 10px;
  border: 1px solid #ccc;
}

.input-group input[type="text"],
.date-group input[type="date"] {
  border: none;
  outline: none;
  padding: 8px 10px;
  font-size: 16px;
  width: 100%;
}

.input-icon img {
  width: 20px;
  height: 20px;
}

.button-date {
  padding: 10px 20px;
  border-radius: 20px;
  border: none;
  cursor: pointer;
  color: white;
  background-color: #0C5873;
  font-size: 16px;
  margin-left: 10px;
}

.button-date {
  background-color: #0C5873;
}

.button-date:hover {
  background-color: #001c4c;
}

</style>