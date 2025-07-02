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
.navbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  background-color: #0e4c69;
  color: white;
  padding: 1rem 2rem;
  position: relative;
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
