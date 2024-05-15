<<template>

  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=EB+Garamond:ital,wght@0,400..800;1,400..800&family=Merriweather:ital,wght@0,300;0,400;0,700;0,900;1,300;1,400;1,700;1,900&display=swap" rel="stylesheet">
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=EB+Garamond:ital,wght@0,400..800;1,400..800&family=Merriweather:ital,wght@0,300;0,400;0,700;0,900;1,300;1,400;1,700;1,900&family=Playfair+Display:ital,wght@0,400..900;1,400..900&display=swap" rel="stylesheet">

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
</template>

<script setup>
// Declaración de la URL de la imagen como una referencia reactiva
const newsImageUrl = 'https://i0.wp.com/newspack-yucatan.s3.amazonaws.com/uploads/2018/08/01DYNA110818C.jpg?w=738&ssl=1';

const goToPrevious = () => {
  // Lógica para ir a la noticia anterior
};

const goToNext = () => {
  // Lógica para ir a la noticia siguiente
};
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

</style>
