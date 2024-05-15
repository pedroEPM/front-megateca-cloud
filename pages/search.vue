<template>
  <div class="time-machine">
    <h1 class="title">Tal día como hoy</h1>
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
</template>

<script>
export default {
  data() {
    return {
      bannerData: [
        {
          title: 'Hoy hace 1 año',
          date: 'Sábado 22/04/2023',
          imageUrl: 'https://www.researchgate.net/publication/308672944/figure/fig2/AS:661144935075852@1534640644734/Pdf-file-newspaperpdf.png',
          link: 'URL_TO_EJEMPLAR_1'
        },
        {
          title: 'Hace 5 años',
          date: 'Lunes 22/04/2019',
          imageUrl: 'https://i.pinimg.com/736x/9b/01/15/9b01150a5eb3aa516de32acd0c4091db.jpg',
          link: 'URL_TO_EJEMPLAR_2'
        },
        {
          title: 'Hace 10 años',
          date: 'Martes 22/04/2014',
          imageUrl: 'https://files.magzter.com/resize/magazine/1588175106/1603501047/view/3.jpg',
          link: 'URL_TO_EJEMPLAR_3'
        },
        {
          title: 'Hace 20 años',
          date: 'Jueves 22/04/2004',
          imageUrl: 'https://www.researchgate.net/publication/308672944/figure/fig2/AS:661144935075852@1534640644734/Pdf-file-newspaperpdf.png',
          link: 'URL_TO_EJEMPLAR_4'
        },
        {
          title: 'Hace 50 años',
          date: 'Viernes 22/04/1974',
          imageUrl: 'https://i.pinimg.com/736x/9b/01/15/9b01150a5eb3aa516de32acd0c4091db.jpg',
          link: 'URL_TO_EJEMPLAR_5'
        },
        {
          title: 'Hace 100 años',
          date: 'Domingo 22/04/1924',
          imageUrl: 'https://files.magzter.com/resize/magazine/1588175106/1603501047/view/3.jpg',
          link: 'URL_TO_EJEMPLAR_6'
          }
      ]
    }
  }
}
</script>

<style scoped>
.time-machine{
  max-width: 1200px;
  margin: auto;
  text-align: center;
}

.title {
  font-family: 'Source Sans Pro', sans-serif;
  margin-bottom: 0;
  padding-bottom: 10px;

}

h1 {
  text-align: left;
  color: #333333;
  margin-bottom: 10px;
}

.newspapers {
  display: flex;
  justify-content: space-around;
  flex-wrap: wrap;
  margin-top: 0;
}

.newspaper {
  width: 30%;
  margin: 10px;
  padding: 20px;
  background: #fff;
  border-radius: 10px;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.date-box {
  font-family: 'Source Sans Pro', sans-serif;
  border-radius: 5px;
  padding: 10px;
  width: 100%;
  margin-bottom: 10px;
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

.image {
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
  width: 200px;
  height: 280px;
  object-fit: cover;
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
  font-size: 11px;
  font-weight: bold;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.2);
  cursor: pointer;
}

.link:hover {
  background: #4F89B9;
}
</style>
