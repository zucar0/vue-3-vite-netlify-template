<!-- <script>
  import { ref } from 'vue'
  import { useKeenSlider } from 'keen-slider/vue'  

  export default {
    setup() {
        const currentSlide = ref(0)
        const sliderInstance = ref(null)
      const [container] = useKeenSlider(
        { 
            loop: true,
            slideChanged(s) {
            currentSlide.value = s.track.details.rel
            },
            created(s) {
            sliderInstance.value = s
            }, 
        }, [
        // add plugins here
        
      ])
      return { container, currentSlide, sliderInstance }
    },
  }
</script>

<template>
  <div class="navigation-wrapper">
    <div ref="container" class="keen-slider">
      <div class="keen-slider__slide number-slide1">1</div>
      <div class="keen-slider__slide number-slide2">2</div>
      <div class="keen-slider__slide number-slide3">3</div>
      <div class="keen-slider__slide number-slide4">4</div>
      <div class="keen-slider__slide number-slide5">5</div>
      <div class="keen-slider__slide number-slide6">6</div>
    </div>

     Flechas 
    <button @click="sliderInstance?.prev()" class="arrow left">‹</button>
    <button @click="sliderInstance?.next()" class="arrow right">›</button>

     Dots 
    <div class="dots">
      <button
        v-for="(_, idx) in sliderInstance?.track?.details?.slides.length || 0"
        :key="idx"
        :class="{ active: currentSlide === idx }"
        @click="sliderInstance.moveToIdx(idx)"
      />
    </div>
  </div>
</template>

<style>
  @import url('keen-slider/keen-slider.css');
  .navigation-wrapper {
  position: relative;
}

.arrow {
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  z-index: 10;
  background: #fff;
  border: none;
  font-size: 2rem;
  padding: 0.5rem;
  cursor: pointer;
}
.arrow.left {
  left: 10px;
}
.arrow.right {
  right: 10px;
}

.dots {
  display: flex;
  justify-content: center;
  margin-top: 10px;
}
.dots button {
  border: none;
  width: 10px;
  height: 10px;
  background: #ccc;
  border-radius: 50%;
  margin: 0 5px;
  padding: 0;
  cursor: pointer;
}
.dots button.active {
  background: #000;
}
</style> -->
<template>
  <div class="navigation-wrapper">
    <div ref="sliderRef" class="keen-slider">
      <div
        v-for="(slide, index) in slides"
        :key="index"
        class="keen-slider__slide slide-card"
      >
        <img :src="slide.image" :alt="slide.title" class="slide-image" />
        <div class="slide-content">
          <h3 class="playfair-display-hero hero">{{ slide.title }}</h3>
          <button>
            <p >{{ slide.text }}</p>
          </button>  
        </div>
      </div>
    </div>

    <!-- Flechas con íconos estilizados -->
    <span class="arrow left" @click="sliderInstance?.prev()">&#10094;</span>
    <span class="arrow right" @click="sliderInstance?.next()">&#10095;</span>
  </div>
</template>

<script setup>
import { ref, onMounted, onBeforeUnmount } from 'vue'
import KeenSlider from 'keen-slider'
import img1 from '../assets/slide/1.png'
import img2 from '../assets/slide/2.png'
import img3 from '../assets/slide/3.png'

const slides = [
  {
    image: img1,
    title: 'Explora el mundo con nosotros',
    text: 'Reserva tu viaje',
  },
  {
    image: img2,
    title: 'Slide Dos',
    text: 'Texto del segundo slide.',
  },
  {
    image: img3,
    title: 'Slide Tres',
    text: 'Contenido del tercer slide.',
  },
]

const sliderRef = ref(null)
const sliderInstance = ref(null)

onMounted(() => {
  sliderInstance.value = new KeenSlider(sliderRef.value, {
    loop: false,
    slides: {
      perView: 1,
      spacing: 15,
    },
  })
})

onBeforeUnmount(() => {
  if (sliderInstance.value) sliderInstance.value.destroy()
})
</script>

<style scoped>
@import 'keen-slider/keen-slider.min.css';

.playfair-display-hero {
  font-family: "Playfair Display", serif;
  font-optical-sizing: auto;
  font-weight: 400;
  font-style: normal;
  font-size: 2rem;
}

.poppins-thin {
  font-family: "Poppins", sans-serif;
  font-weight: 100;
  font-style: normal;
}

.poppins-extralight {
  font-family: "Poppins", sans-serif;
  font-weight: 200;
  font-style: normal;
}

.poppins-light {
  font-family: "Poppins", sans-serif;
  font-weight: 300;
  font-style: normal;
}

.poppins-regular {
  font-family: "Poppins", sans-serif;
  font-weight: 400;
  font-style: normal;
}

.poppins-medium {
  font-family: "Poppins", sans-serif;
  font-weight: 500;
  font-style: normal;
}

.poppins-semibold {
  font-family: "Poppins", sans-serif;
  font-weight: 600;
  font-style: normal;
}

.poppins-bold {
  font-family: "Poppins", sans-serif;
  font-weight: 700;
  font-style: normal;
}

.poppins-extrabold {
  font-family: "Poppins", sans-serif;
  font-weight: 800;
  font-style: normal;
}

.poppins-black {
  font-family: "Poppins", sans-serif;
  font-weight: 900;
  font-style: normal;
}

.poppins-thin-italic {
  font-family: "Poppins", sans-serif;
  font-weight: 100;
  font-style: italic;
}

.poppins-extralight-italic {
  font-family: "Poppins", sans-serif;
  font-weight: 200;
  font-style: italic;
}

.poppins-light-italic {
  font-family: "Poppins", sans-serif;
  font-weight: 300;
  font-style: italic;
}

.poppins-regular-italic {
  font-family: "Poppins", sans-serif;
  font-weight: 400;
  font-style: italic;
}

.poppins-medium-italic {
  font-family: "Poppins", sans-serif;
  font-weight: 500;
  font-style: italic;
}

.poppins-semibold-italic {
  font-family: "Poppins", sans-serif;
  font-weight: 600;
  font-style: italic;
}

.poppins-bold-italic {
  font-family: "Poppins", sans-serif;
  font-weight: 700;
  font-style: italic;
}

.poppins-extrabold-italic {
  font-family: "Poppins", sans-serif;
  font-weight: 800;
  font-style: italic;
}

.poppins-black-italic {
  font-family: "Poppins", sans-serif;
  font-weight: 900;
  font-style: italic;
}


.navigation-wrapper {
  position: relative;
}

.keen-slider__slide {
  display: flex;
  flex-direction: column;
  align-items: center;
  background: #fff;
  overflow: hidden;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
}

.slide-image {
  width: 100%;
  height: 910px;
  object-fit: cover;
  display: block;
}

.slide-content {
  padding: 1rem;
  text-align: left;
  position: absolute;
  top: 20%;
  width: 70%;
}

.slide-content button {
  border-radius: 10px;
  border: 1px solid #EFB7AC;
  background: #EFB7AC;
  color: white;
}

.slide-content h3 {
  font-size: 1.25rem;
}

.slide-content h3.hero {
  font-size: 3.25rem;
  width: 50%;
  font-weight: bold;
  color: #EFB7AC;
}

.slide-content p {
  color: white;
  padding: 1px 10px;
}

/* Flechas estilizadas */
.arrow {
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  font-size: 2.5rem;
  color: #EFB7AC;
  padding: 0.25rem 0.6rem;
  border-radius: 50%;
  cursor: pointer;
  user-select: none;
  transition: background 0.2s, transform 0.2s;
  z-index: 10;
}
.arrow:hover {
  transform: translateY(-50%) scale(1.1);
}
.arrow.left {
  left: 10px;
}
.arrow.right {
  right: 10px;
}
</style>
