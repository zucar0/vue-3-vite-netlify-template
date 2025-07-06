<template>
    <div class="destinations">
        <div class="subtitle">
            <h3 class="subtitle playfair-display">
                Destinos populares
            </h3>
        </div>
        <div class="grid">
            <!-- <div class="card">
                <img src="https://source.unsplash.com/400x300/?paris" alt="Paris">
                <div class="card-content">
                <h3>París</h3>
                <p>Desde $999</p>
                </div>
            </div>
            <div class="card">
                <img src="https://source.unsplash.com/400x300/?tokyo" alt="Tokyo">
                <div class="card-content">
                <h3>Tokyo</h3>
                <p>Desde $1299</p>
                </div>
            </div>
            <div class="card">
                <img src="https://source.unsplash.com/400x300/?beach" alt="Playa del Carmen">
                <div class="card-content">
                <h3>Playa del Carmen</h3>
                <p>Desde $399</p>
                </div>
            </div> -->

            <div
                v-for="(destine, index) in destinations"
                :key="index" class="card-content">
                <img :src="destine.img" :alt="destine.text" class="destine-image" />
                <h3>{{ destine.text }}</h3>
                <p>Desde $ {{ destine.price }}</p>
            </div>

        </div>
    </div>
</template>
<script setup>
import destinations1 from '../assets/destinations/paris-thumbnail.png'
import destinations2 from '../assets/destinations/tokyo-thumbnail.png'
import destinations3 from '../assets/destinations/playa-del-carmen-thmbnail.png'

const destinations = [
  {
    img: destinations1,
    price: '999',
    text: 'París',
  },
  {
    img: destinations2,
    price: '1299',
    text: 'Tokio',
  },
  {
    img: destinations3,
    price: '399',
    text: 'Playa del Carmen',
  },
]
</script>
<style scoped>
    .playfair-display {
    font-family: "Playfair Display", serif;
    font-optical-sizing: auto;
    font-weight: 400;
    font-style: normal;
    font-size: 2rem;
    }

    .destinations{
        background-color: #ACE4EF;
        padding: 2rem;
    }
    .destinations h3{
        margin: 0;
        padding: 15px 0;
        text-align: left;
        color: #EFB7AC;
    }

    .destinations .destine-image{
        border-radius: 20px;
        max-width: 300px;
    }

    .destinations div.subtitle{
        width: 50%;
        margin: 0 auto;
    }
     section {
      padding: 3rem 2rem;
      max-width: 1100px;
      margin: auto;
      background-color: #ACE4EF;
      color: #0E4C69;
    }

    .grid {
      display: flex;
      gap: 1.5rem;
      flex-wrap: wrap;
      justify-content: center;
      margin-top: 1.5rem;
    }

    .card {
      /* background: #FFFFFF;
      box-shadow: 0 2px 8px rgba(0,0,0,0.1);
      */
      border-radius: 10px;
      overflow: hidden;
      width: 100%;
      max-width: 300px;
      color: #1a1a1a;
    }

    .card img {
      width: 100%;
      height: 180px;
      object-fit: cover;
      box-shadow: 0 2px 8px rgba(0,0,0,0.1);
    }

    .card-content {
      padding: 1rem;
    }

    .card-content h3{
      color: #0E4C69;
      text-align: center;
    }

    .card .content p {
        color: #2A2F33;
    }

    h2 {
      color: #EFB7AC;
      margin-bottom: 1rem;
    }
</style>