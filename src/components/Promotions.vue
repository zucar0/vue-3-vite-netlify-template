<template>
    <div class="promotions">
        <h3 class="playfair-display-promo">
            Promociones destacadas
        </h3>
        <div class="info">
            <ul>
                <li>
                    Verano en Cancún: 40% de descuento
                </li>
                <li>
                    Paquete Europeo:  2 x 1
                </li>
            </ul>
            <div class="button-container">
                <a href="/index.html" class="btn">
                    <button>
                        Ver todas las promociones
                    </button>
                </a>
            </div>
        </div>
        <div
            v-for="(promo, index) in promocional"
            :key="index" class="banner">
            <img :src="promo.img" :alt="promo.text" class="promo-image" />
        </div>
    </div>
</template>
<script setup>
    import banner from '../assets/banners/banner-promocional.jpg'
    const promocional = [
    {
        img: banner,
        text: 'Banner promocional'
    } 
]
</script>
<style scoped>
    .playfair-display-promo {
        font-family: "Playfair Display", serif;
        font-optical-sizing: auto;
        font-weight: 400;
        font-style: normal;
        font-size: 2rem;
        color: #EFB7AC;
    }
    .promotions .info{
        width: 50%;
        margin: 0 auto 30px auto;
    }
    .promotions .info ul li{
        text-align: left;
    }
    .promotions .info ul li::marker{
        color: #4f93b6;
        font-size: 1.5rem;
    }
    .promotions .info .button-container{
        /*width: 50%;*/
        margin: 0 auto;
        text-align: right;
    }
    .promotions .info .button-container .btn{
        cursor: pointer;
    }
    .promotions .info button{
        background-color: #4f93b6;
        color: white;
        border-radius: 8px;
        border: none;
        padding: 20px;
        font-size: 1.15rem;
    }
    .promotions h3{
        width: 50%;
        margin: 2rem auto;
        text-align: left;
    }
    .promotions .banner img{
        max-width: 70%;
        width: 100%;
        border-radius: 10px;
    }
    .promotions .banner{
        margin-bottom: 2rem;
    }
</style>