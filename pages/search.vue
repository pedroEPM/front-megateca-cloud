<template>

    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin="">
    <link href="https://fonts.googleapis.com/css2?family=Anton&family=Great+Vibes&family=Lora:ital,wght@0,400..700;1,400..700&family=Oswald&family=Roboto:ital,wght@0,100;0,300;0,400;0,500;0,700;0,900;1,100;1,300;1,400;1,500;1,700;1,900&display=swap" rel="stylesheet">
  
      <footer class="footer">
        <div class="social-media">
          <img src="@/pages/images/facebook.png" alt="Facebook"/>
          <img src="@/pages/images/twitter.png" alt="Twitter"/>
          <img src="@/pages/images/instagram.png" alt="Instagram"/>
          <img src="@/pages/images/youtube.png" alt="YouTube"/>
        </div>
  
        <div class="logo">
          <img src="@/pages/images/logoDiario.png" alt="Diario de Yucatán">
        </div>
  
        <div class="navigation">
          <button @click="login" style="color: black; font-weight: bold;">Iniciar Sesión</button>
          <button @click="subscribe" style="background-color: #0C5873;color: white;">Suscríbete</button>
          <button @click="search" class="search-button">
            <img src="@/pages/images/búsqueda.png" alt="Buscar">
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
            <img src="@/pages/images/búsqueda.png" alt="Buscar"/>
          </span>
          <input type="text" placeholder="Buscar" v-model="searchQuery">
        </div>
        <div class="date-group">
          <input type="date" v-model="startDate" placeholder="Fecha inicial">
          <input type="date" v-model="endDate" placeholder="Fecha final">
        </div>
        <button class="button-date" @click="searchByDate">Buscar</button>
      </div>
  
      <div class="time-machine">
      <h1 class="main-title">Tal día como hoy</h1>
      <div class="newspapers">
        <div class="newspaper" v-for="(item, index) in bannerData" :key="index">
          <div class="date-box">
            <h2 class="date">{{ item.title }}</h2>
            <p class="date-sub">{{ item.date }}</p>
          </div>
          <img class="image" :src="item.imageUrl" :alt="`Cover from ${item.title}`">
          <a class="link" :href="item.link" target="_blank">VER EJEMPLAR</a>
        </div>
  
      </div>
    </div>
  
      <footer class="footer-container">
          <div class="footer-links">
            <img src="@/pages/images/footer-mega-media.png" alt="Grupo Megamedia" class="footer-logo" style="width: 180px; height: auto;">
            <a href="/sociales"><img src="@/pages/images/footer-logo-sociales.png" alt="Sociales" class="link-icon" style="width: 70px; height: 10px;"></a>
            <a href="/planb"><img src="@/pages/images/footer-logo-9.png" alt="Plan B" class="link-icon" style="width: auto; height: auto;"></a>
            <a href="/avisoseconomicos"><img src="@/pages/images/footer-logo-2-1.png" alt="Avisos Económicos" class="link-icon" style="width: auto; height: auto;"></a>
            <a href="/cmujer"><img src="@/pages/images/footer-logo-3-1.png" alt="C Mujer" class="link-icon" style="width: auto; height: auto;"></a>
            <a href="/descubro"><img src="@/pages/images/footer-logo-4.png" alt="Descubro" class="link-icon" style="width: auto; height: auto;"></a>
            <a href="/meganews"><img src="@/pages/images/footer-logo-5.png" alt="Mega News" class="link-icon" style="width: auto; height: auto;"></a>
            <a href="/empleate"><img src="@/pages/images/footer-logo-8-2.png" alt="Empléate" class="link-icon" style="width: auto; height: auto;"></a>
            <a href="/megashop"><img src="@/pages/images/footer-logo-7.png" alt="Mega Shop" class="link-icon" style="width: auto; height: auto;"></a>
            <a href="/alchile"><img src="@/pages/images/footer-logo-1-1.png" alt="Al Chile" class="link-icon" style="width: auto; height: auto;"></a>
          </div>
      </footer>
  
      <footer class="footer-container2">
  
          <div class="footer-bottom">
            <p>Prohibida su reproducción total o parcial, así como su traducción a cualquier idioma sin autorización escrita de su titular.</p>
            <p>© 2024 Derechos Reservados Diario Yucatán. Powered by DimitriMedNov</p>
          </div>
  
          <div class="social-links">
            <a href="http://facebook.com"><img src="@/pages/images/facebookblanco.png" alt="Facebook"></a>
            <a href="http://twitter.com"><img src="@/pages/images/twitterblanco.png" alt="Twitter"></a>
            <a href="http://instagram.com"><img src="@/pages/images/instagramblanco.png" alt="Instagram"></a>
          </div>
  
        </footer>
  
  </template>
  
  <script>
  export default {
    data() {
      return {
        bannerData: [
          {
            title: 'Hoy hace 1 año',
            date: 'Sábado 22/04/2023',
            imageUrl: 'https://i0.wp.com/newspack-yucatan.s3.amazonaws.com/uploads/2018/08/01DYNA110818C.jpg?w=738&ssl=1',
            link: 'URL_TO_EJEMPLAR_1'
  
          },
          {
            title: 'Hace 5 años',
            date: 'Lunes 22/04/2019',
            imageUrl: 'https://i0.wp.com/newspack-yucatan.s3.amazonaws.com/uploads/2018/08/01DYNA100818C.jpg?w=738&ssl=1',
            link: 'URL_TO_EJEMPLAR_2'
          },
          {
            title: 'Hace 10 años',
            date: 'Martes 22/04/2014',
            imageUrl: 'https://i0.wp.com/newspack-yucatan.s3.amazonaws.com/uploads/2018/08/01DYNA090818C.jpg?w=738&ssl=1',
            link: 'URL_TO_EJEMPLAR_3'
          },
          {
            title: 'Hace 20 años',
            date: 'Jueves 22/04/2004',
            imageUrl: 'https://i0.wp.com/newspack-yucatan.s3.amazonaws.com/uploads/2018/08/01DYNA080818C.jpg?w=738&ssl=1',
            link: 'URL_TO_EJEMPLAR_4'
          },
          {
            title: 'Hace 25 años',
            date: 'Viernes 22/04/1974',
            imageUrl: 'https://i0.wp.com/newspack-yucatan.s3.amazonaws.com/uploads/2018/08/01DYNA070818C.jpg?w=738&ssl=1',
            link: 'URL_TO_EJEMPLAR_5'
          },
          {
            title: 'Hace 50 años',
            date: 'Domingo 22/04/1924',
            imageUrl: 'https://i0.wp.com/newspack-yucatan.s3.amazonaws.com/uploads/2018/08/01DYNA040818C.jpg?w=738&ssl=1',
            link: 'URL_TO_EJEMPLAR_6'
            },
            {
            title: 'Hace 75 años',
            date: 'Domingo 22/04/1824',
            imageUrl: 'https://imgs.search.brave.com/j0qBfHsURuhg6yHedI3b6jEIIy8zmx0_M8H1-hGucR4/rs:fit:860:0:0/g:ce/aHR0cHM6Ly9pbWcu/a2lvc2tvLm5ldC8y/MDI0LzA0LzE5L214/L214X2RpYXJpb195/dWNhdGFuLjc1MC5q/cGc',
            link: 'URL_TO_EJEMPLAR_6'
            },
            {
            title: 'Hace 100 años',
            date: 'Domingo 22/04/1724',
            imageUrl: 'https://megateca.s3.amazonaws.com/1927/1/1/01DYCS010127B.jpg',
            link: 'URL_TO_EJEMPLAR_6'
            }
        ]
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
    margin-top: 20px;
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