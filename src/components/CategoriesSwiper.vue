<template>
     <div class="categories__content-swiper">
        <swiper
            :slidesPerView="'auto'"
            :spaceBetween="30"
            :loop="true"
            :navigation="true"
            :modules="modules"
            class="categories-mySwiper"
        >
        <swiper-slide>
            <div class="categories__slide">
                <a href="#" class="categories__slide-link"></a>
                <img class="categories__slide-logo" src="/src/assets/categories-swiper.png" alt="">
                <p class="categories__slide-name">Phones</p>
            </div>
        </swiper-slide>
        <swiper-slide>
            <div class="categories__slide">
                <a href="#" class="categories__slide-link"></a>
                <img class="categories__slide-logo" src="/src/assets/categories-swiper.png" alt="">
                <p class="categories__slide-name">Phones</p>
            </div>
        </swiper-slide>
        <swiper-slide>
            <div class="categories__slide">
                <a href="#" class="categories__slide-link"></a>
                <img class="categories__slide-logo" src="/src/assets/categories-swiper.png" alt="">
                <p class="categories__slide-name">Phones</p>
            </div>
        </swiper-slide>
        <swiper-slide>
            <div class="categories__slide">
                <a href="#" class="categories__slide-link"></a>
                <img class="categories__slide-logo" src="/src/assets/categories-swiper.png" alt="">
                <p class="categories__slide-name">Phones</p>
            </div>
        </swiper-slide>
        <swiper-slide>
            <div class="categories__slide">
                <a href="#" class="categories__slide-link"></a>
                <img class="categories__slide-logo" src="/src/assets/categories-swiper.png" alt="">
                <p class="categories__slide-name">Phones</p>
            </div>
        </swiper-slide>
        <swiper-slide>
            <div class="categories__slide">
                <a href="#" class="categories__slide-link"></a>
                <img class="categories__slide-logo" src="/src/assets/categories-swiper.png" alt="">
                <p class="categories__slide-name">Phones</p>
            </div>
        </swiper-slide>
        <swiper-slide>
            <div class="categories__slide">
                <a href="#" class="categories__slide-link"></a>
                <img class="categories__slide-logo" src="/src/assets/categories-swiper.png" alt="">
                <p class="categories__slide-name">Phones</p>
            </div>
        </swiper-slide>

    </swiper>
    </div>
</template>
<script>
  // Import Swiper Vue.js components
  import { Swiper, SwiperSlide } from 'swiper/vue';

  // Import Swiper styles
  import 'swiper/css';



  // import required modules
  import { Pagination } from 'swiper/modules';

  export default {
    components: {
      Swiper,
      SwiperSlide,
    },
    setup() {
      return {
        modules: [Pagination],
      };
    },
  };
</script>
<style>
.categories__content-swiper .swiper-slide {
    max-width: 14.5%;
    height: 145px;  
}
.categories__slide {
    position: relative;
    padding: 35px 0;
    border: 1px solid rgba(0, 0, 0, 0.3);
    border-radius: 4px;
    width: 100%;
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: space-between;
    flex-direction: column;
}
.categories__slide-link {
    position: absolute;
    width: 100%;
    height: 100%;
    top: 0;
    left: 0;
}
.categories__slide-name {
    font-family: "Poppins", sans-serif;
    font-weight: 400;
    font-size: 16px;
    line-height: 1.5;
    color: #000;
}
@media (max-width: 768px) {
  .categories__content-swiper .swiper-slide {
    max-width: 20.5%;
  }
}
@media (max-width: 425px) {
    .categories__content-swiper .swiper-slide {
    max-width: 40.5%;
  }
}
</style>