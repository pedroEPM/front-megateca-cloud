<template>
  <div class="container">
    <div class="header">
      <span class="arrow left">❮</span>

      <div class="details">
        <div class="date">08/05/2023</div>
        <div class="edition">Edición LAVG Barcelona</div>
        <div class="pages">56 Páginas</div>
        <div class="year">Año 2023</div>
      </div>
      <span class="arrow right">❯</span>
    </div>
    <div class="actions">
      <button class="all-covers">VER TODAS LAS PORTADAS</button>
    </div>
    <div class="search">
      <input type="text" placeholder="Buscar en la edición">
      <span class="search-icon">🔍</span>
    </div>
    <div class="links">
      <a href="#">VER PORTADA EN PDF</a>
      <a href="#">COMPARTIR EDICIÓN</a>
      <a href="#">DESCARGAR EDICIÓN COMPLETA EN PDF</a>
      <a href="#">IR A LA TIENDA HEMEROTECA</a>
    </div>
  </div>
</template>

<script setup lang="ts">
// Script section
</script>

<style scoped>
.container {
  background: #FFFFFF;
  padding: 20px;
  border-radius: 10px;
  box-shadow: 0 4px 8px rgba(0,0,0,0.1);
}

.header {
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.arrow {
  font-size: 24px;
  cursor: pointer;
}

.details {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.date, .edition, .pages, .year {
  font-size: 16px;
  color: #333;
}

.actions {
  margin-top: 10px;
  display: flex;
  justify-content: center;
}

.all-covers {
  background-color: #0056b3;
  color: white;
  border: none;
  padding: 10px 20px;
  cursor: pointer;
  border-radius: 5px;
}

.search {
  margin-top: 20px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.search input {
  padding: 10px;
  margin-right: 5px;
  border: 1px solid #ccc;
  border-radius: 5px;
}

.search-icon {
  background-color: #0056b3;
  color: white;
  padding: 10px;
  border-radius: 50%;
  cursor: pointer;
}

.links {
  margin-top: 20px;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.links a {
  color: #0056b3;
  text-decoration: none;
  margin: 5px 0;
}
</style>

