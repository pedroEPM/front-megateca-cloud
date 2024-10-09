<template>

  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin="">
  <link href="https://fonts.googleapis.com/css2?family=Anton&family=Great+Vibes&family=Lora:ital,wght@0,400..700;1,400..700&family=Oswald&family=Roboto:ital,wght@0,100;0,300;0,400;0,500;0,700;0,900;1,100;1,300;1,400;1,500;1,700;1,900&display=swap" rel="stylesheet">
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=EB+Garamond:ital,wght@0,400..800;1,400..800&family=Merriweather:ital,wght@0,300;0,400;0,700;0,900;1,300;1,400;1,700;1,900&display=swap" rel="stylesheet">
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=EB+Garamond:ital,wght@0,400..800;1,400..800&family=Merriweather:ital,wght@0,300;0,400;0,700;0,900;1,300;1,400;1,700;1,900&family=Playfair+Display:ital,wght@0,400..900;1,400..900&display=swap" rel="stylesheet">

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
          <img src="@/public/búsqueda.png" alt="Buscar">
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
          <img src="@/public/búsqueda.png" alt="Buscar"/>
        </span>
        <input type="text" placeholder="Buscar" v-model="searchQuery">
      </div>
      <div class="date-group">
        <input type="date" v-model="startDate" placeholder="Fecha inicial">
        <input type="date" v-model="endDate" placeholder="Fecha final">
      </div>
      <button class="button-date" @click="searchByDate">Buscar</button>
    </div>

    <div class="news-display">

    <div class="news-image">
      <img :src="newsImageUrl" alt="Portada de La Vanguardia">
    </div>

    <div class="news-details">

      <div class="details">

        <div class="button-container">
          <button type="button" class="svg-button">
            <svg class="w-6 h-6 text-gray-800 dark:text-white" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" width="24" height="24" fill="none" viewBox="0 0 24 24">
              <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="m15 19-7-7 7-7"/>
            </svg>
          </button>
          <div class="date">22/04/2023</div>
          <button type="button" class="svg-button">
            <svg class="w-6 h-6 text-gray-800 dark:text-white" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" width="24" height="24" fill="none" viewBox="0 0 24 24">
              <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="m9 5 7 7-7 7"/>
            </svg>
          </button>
        </div>

        <div class="edition">Edición</div>
        <div class="subedition">Diario de Yucatan</div>
        <div class="pages">Páginas</div>
        <div class="subpages">56</div>
        <div class="year">Año</div>
        <div class="subyear">2023</div>
      </div>

      <div class="actions">
        <button class="all-covers">VER TODAS LAS PORTADAS</button>
      </div>

      <div class="search-box">
        <input type="text" placeholder="Buscar en la edición">
        <button>Buscar</button>
      </div>

      <div class="additional-links">

        <span class="flex items-center">
          <svg class="w-6 h-6 text-gray-800 dark:text-white" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" width="24" height="24" fill="none" viewBox="0 0 24 24">
            <path stroke="currentColor" stroke-width="2" d="M21 12c0 1.2-4.03 6-9 6s-9-4.8-9-6c0-1.2 4.03-6 9-6s9 4.8 9 6Z"/>
            <path stroke="currentColor" stroke-width="2" d="M15 12a3 3 0 1 1-6 0 3 3 0 0 1 6 0Z"/>
          </svg>
          <span class="ml-2">Ver portada en PDF</span>
        </span>

        <span class="flex items-center">
          <svg class="w-6 h-6 text-gray-800 dark:text-white" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" width="24" height="24" fill="currentColor" viewBox="0 0 24 24">
            <path d="M17.5 3a3.5 3.5 0 0 0-3.456 4.06L8.143 9.704a3.5 3.5 0 1 0-.01 4.6l5.91 2.65a3.5 3.5 0 1 0 .863-1.805l-5.94-2.662a3.53 3.53 0 0 0 .002-.961l5.948-2.667A3.5 3.5 0 1 0 17.5 3Z"/>
          </svg>
          <span class="ml-2">Compartir Edicion</span>
        </span>

        <span class="flex items-center">
          <svg class="w-6 h-6 text-gray-800 dark:text-white" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" width="24" height="24" fill="currentColor" viewBox="0 0 24 24">
            <path fill-rule="evenodd" d="M13 11.15V4a1 1 0 1 0-2 0v7.15L8.78 8.374a1 1 0 1 0-1.56 1.25l4 5a1 1 0 0 0 1.56 0l4-5a1 1 0 1 0-1.56-1.25L13 11.15Z" clip-rule="evenodd"/>
            <path fill-rule="evenodd" d="M9.657 15.874 7.358 13H5a2 2 0 0 0-2 2v4a2 2 0 0 0 2 2h14a2 2 0 0 0 2-2v-4a2 2 0 0 0-2-2h-2.358l-2.3 2.874a3 3 0 0 1-4.685 0ZM17 16a1 1 0 1 0 0 2h.01a1 1 0 1 0 0-2H17Z" clip-rule="evenodd"/>
          </svg>
          <span class="ml-2">Descargar Edicion Completa en PDF</span>
        </span>

        <span class="flex items-center">
          <svg class="w-6 h-6 text-gray-800 dark:text-white" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" width="24" height="24" fill="currentColor" viewBox="0 0 24 24">
          <path fill-rule="evenodd" d="M14 7h-4v3a1 1 0 0 1-2 0V7H6a1 1 0 0 0-.997.923l-.917 11.924A2 2 0 0 0 6.08 22h11.84a2 2 0 0 0 1.994-2.153l-.917-11.924A1 1 0 0 0 18 7h-2v3a1 1 0 1 1-2 0V7Zm-2-3a2 2 0 0 0-2 2v1H8V6a4 4 0 0 1 8 0v1h-2V6a2 2 0 0 0-2-2Z" clip-rule="evenodd"/>
        </svg>
          <span class="ml-2">Ir a MegaShop</span>
        </span>

      </div>
    </div>
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
        <p>© 2024 Derechos Reservados Diario Yucatán. Powered by DimitriMedNov</p>
      </div>

      <div class="social-links">
        <a href="http://facebook.com"><img src="@/public/facebookblanco.png" alt="Facebook"></a>
        <a href="http://twitter.com"><img src="@/public/twitterblanco.png" alt="Twitter"></a>
        <a href="http://instagram.com"><img src="@/public/instagramblanco.png" alt="Instagram"></a>
      </div>

    </footer>

</template>

<script>
export default {
  data() {
    return {
      newsImageUrl: 'https://i0.wp.com/newspack-yucatan.s3.amazonaws.com/uploads/2018/08/01DYNA110818C.jpg?w=738&ssl=1' // Agregando la variable
    }
  },
  methods: {
    searchByText() {
      console.log("Buscando por texto:", this.searchQuery);
    },
    searchByDate() {
      console.log("Buscando desde:", this.startDate, "hasta:", this.endDate);
    }
  }
}
</script>

<style scoped>

.news-display {
  display: flex;
  justify-content: space-between;
  padding: 20px;
  background-color: #fff;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
}

.news-image img {
  width: 100%;
  max-width: 600px;
}

.news-details {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.date-info h3, .date-info p {
  margin: 5px 0;
}

.news-controls button {
  background: none;
  border: none;
  font-size: 24px;
  cursor: pointer;
}

.search-box {
  padding: 20px;
}

.search-box input[type="text"] {
  padding: 10px;
  margin-right: 10px;
  border: 1px solid black;
  border-radius: 20px;
}

.search-box button {
  margin-top: 20px;
  padding: 10px 20px;
  background-color: #0C5873;
  color: white;
  border-radius: 20px;
  cursor: pointer;
}
.search-box button:hover {
  background-color: #001c4c;
}

.additional-links {
  display: flex;
  flex-direction: column;
  margin: 5px 0;
  color: #0C5873;
}
.additional-links svg {
  width: 42px; /* Ajusta este valor */
  height: 42px; /* Ajusta este valor */
}

.actions button{
  margin-top: 20px;
  font-size: 13px;
  background-color: #0C5873;
  color: white;
  border: none;
  padding: 11px;
  cursor: pointer;
  border-radius: 15px;
}

.actions button:hover {
  background-color: #001c4c;
}

.details {
  display: flex;
  flex-direction: column;
}

.date {
  font-size: 50px;
  color: #0C5873;
  font-family: "Merriweather", serif;
  padding-left: 20px;
  padding-right: 20px;
}

.edition, .subedition, .pages, .subpages, .year, .subyear{
  font-family: "Playfair Display", serif;
  text-align: center;
  font-size: 20px;
  color: #0C5873;
  font-weight: bold;
}
.button-container {
  display: flex;
  align-items: center;
  justify-content: space-between; /* Space buttons evenly */
}

.button-container svg {
  width: 60px;
  height: 60px;
  color: #0C5873;
}

.svg-button {
  border: none;
  background: none;
  padding: 0;
  cursor: pointer; /* Indicate clickable element */
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
  margin-top: 150px;
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