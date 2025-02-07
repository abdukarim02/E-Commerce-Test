<template>
    <div class="categories__content-swiper">
      <swiper
        :slidesPerView="'auto'"
        :spaceBetween="30"
        :loop="true"
        :navigation="{ prevEl: prevBtn, nextEl: nextBtn }"
        :modules="modules"
        class="categories-mySwiper"
      >
        <swiper-slide v-for="(category, index) in categories" :key="index">
          <div class="categories__slide">
            <a href="#" class="categories__slide-link"></a>
            <img class="categories__slide-logo" src="/src/assets/categories-swiper.png" alt="">
            <p class="categories__slide-name">{{ category }}</p>
          </div>
        </swiper-slide>
      </swiper>
      <div class="categories__navigation">
        <button ref="prevBtn" class="swiper-button-prev">
          <svg width="18" height="16" viewBox="0 0 18 16" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path d="M8 1L1 8L8 15M1 8H17" stroke="black" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
          </svg>
        </button>
        <button ref="nextBtn" class="swiper-button-next">
            <svg width="19" height="16" viewBox="0 0 19 16" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path d="M1.5 8H18M18 8L11 1M18 8L11 15" stroke="black" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
          </svg>
        </button>
      </div>
    </div>
</template>
  
<script>
  import { ref } from 'vue';
  import { Swiper, SwiperSlide } from 'swiper/vue';
  import 'swiper/css';
  import { Navigation } from 'swiper/modules';
  
  export default {
    components: {
      Swiper,
      SwiperSlide,
    },
    setup() {
      const prevBtn = ref(null);
      const nextBtn = ref(null);
  
      return {
        modules: [Navigation],
        prevBtn,
        nextBtn,
        categories: ["Phones", "Laptops", "Tablets", "Watches", "Headphones", "Cameras", "Accessories"]
      };
    },
  };
</script>
  
<style>
.categories__content-swiper .swiper-slide {
    max-width: 14.5%;
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
.categories__navigation {
  width: 100px;
  display: flex;
  gap: 10px;
  justify-content: center;
  margin-top: 20px;
  position: absolute;
  top:  25%;
  right: 2%;
}
.swiper-button-prev,
.swiper-button-next {
    background: transparent;
}
@media (max-width: 768px) {
  .categories__slide {
    padding: 45px 0;
  }
  .categories__content-swiper .swiper-slide {
    max-width: 40.5%;
  }
}
@media (max-width: 910px) {
  .categories__navigation {
        display: none;
    }
}
@media (max-width: 425px) {
    .categories__content-swiper .swiper-slide {
        max-width: 40.5%;
     }
    .categories__content-swiper .swiper-slide {
      max-width: 50.5%;
     }
    
}
</style>