<template>
  <header class="navbar">
    <div class="navbar__brand">
        <img alt="Mebu viajes" src="../assets/mebu-viajes.png" />
    </div>

    <button class="navbar__toggle" @click="menuOpen = !menuOpen">
      ☰
    </button>

    <nav :class="['navbar__menu', { 'is-open': menuOpen }]">
      <a href="/" class="navbar__link">Inicio</a>
      <a href="/nosotros" class="navbar__link">Nosotros</a>
      <a href="/servicios" class="navbar__link">Servicios</a>
      <a href="/contacto" class="navbar__link">Contacto</a>
    </nav>
  </header>
</template>

<script setup>
import { ref } from 'vue'

const menuOpen = ref(false)
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Montserrat:ital,wght@0,100..900;1,100..900&family=Playfair+Display:ital,wght@0,400..900;1,400..900&family=Poppins:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap');

.navbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  color: white;
  padding: 1rem 2rem;
}

.navbar__brand {
  font-size: 1.5rem;
  font-weight: bold;
  text-align: left;
}

.navbar__brand img{
    max-width: 7%;
}

.navbar__toggle {
  display: none;
  background: none;
  border: none;
  font-size: 2rem;
  color: white;
  cursor: pointer;
}

.navbar__menu {
  display: flex;
  gap: 1.5rem;
}

.navbar__link {
  color: white;
  text-decoration: none;
  font-weight: 500;
}

.navbar__link:hover {
  text-decoration: underline;
}

/* Responsive */
@media (min-width: 768px){
    .navbar {
        background-color: transparent;
        position: absolute;
        z-index: 1;
    }
}

/* Responsive */
@media (max-width: 768px) {
  .navbar__toggle {
    display: block;
  }

  .navbar__menu {
    flex-direction: column;
    position: absolute;
    top: 100%;
    left: 0;
    width: 100%;
    background: #0e4c69;
    padding: 1rem 2rem;
    display: none;
  }

  .navbar__menu.is-open {
    display: flex;
  }

  .navbar__brand img{
        max-width: 25%;
    }
}
</style>
