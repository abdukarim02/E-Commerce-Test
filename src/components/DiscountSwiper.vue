<template>
  <div class="discount__swiper">
    <swiper
      :slidesPerView="'auto'"
      :spaceBetween="30"
      :breakpoints="breakpoints"
      :modules="[Navigation]"
      :navigation="{
        prevEl: prevEl,
        nextEl: nextEl
      }"
      class="discount__mySwiper"
    >
      <swiper-slide v-for="product in products" :key="product.id">
        <DiscountCartList
          :title="product.title"
          :price="product.price"
          :discount="product.discount"
          :number="product.number"
          :imag="product.imag"
          :percent="product.percent"
        />
      </swiper-slide>
    </swiper>

    <!-- Кнопки навигации -->
    <div class="discount__navigation">
      <button ref="prevEl" class="swiper-button-prev">
        <svg width="18" height="16" viewBox="0 0 18 16" fill="none" xmlns="http://www.w3.org/2000/svg">
          <path d="M8 1L1 8L8 15M1 8H17" stroke="black" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" />
        </svg>
      </button>
      <button ref="nextEl" class="swiper-button-next">
        <svg width="19" height="16" viewBox="0 0 19 16" fill="none" xmlns="http://www.w3.org/2000/svg">
          <path d="M1.5 8H18M18 8L11 1M18 8L11 15" stroke="black" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round" />
        </svg>
      </button>
    </div>
  </div>

  <a href="#" class="discount__content-btn btn">View All Products</a>
</template>

<script>
import { ref, onMounted } from "vue";
import DiscountCartList from './DiscountCartList.vue';
import { Swiper, SwiperSlide } from 'swiper/vue';
import 'swiper/css';
import 'swiper/css/navigation';
import { Navigation } from 'swiper/modules';

export default {
  components: {
    Swiper,
    SwiperSlide,
    DiscountCartList,
  },
  setup() {
    const prevEl = ref(null);
    const nextEl = ref(null);

    const breakpoints = {
      0: { slidesPerView: 1, spaceBetween: 10 },
      750: { slidesPerView: 2, spaceBetween: 20 },
      1000: { slidesPerView: 3, spaceBetween: 40 },
      1500: { slidesPerView: 4, spaceBetween: 50 },
    };

    const products = [
      {
        id: 1,
        title: "HAVIT HV-G92 Gamepad",
        price: "$120",
        percent: "-40%",
        discount: "$160",
        number: 88,
        imag: "/src/assets/discount__sw-1.png"
      },
      {
        id: 2,
        title: "Logitech G502 Hero",
        price: "$220",
        percent: "-30%",
        discount: "$300",
        number: 56,
        imag: "/src/assets/discount__sw-1.png"
      },
      {
        id: 3,
        title: "Razer BlackWidow",
        price: "$150",
        percent: "-25%",
        discount: "$200",
        number: 72,
        imag: "/src/assets/discount__sw-1.png"
      },
      {
        id: 4,
        title: "SteelSeries Arctis 7",
        price: "$180",
        percent: "-20%",
        discount: "$225",
        number: 35,
        imag: "/src/assets/discount__sw-1.png"
      },
      {
        id: 5,
        title: "Corsair K95 RGB Platinum",
        price: "$199",
        percent: "-15%",
        discount: "$235",
        number: 41,
        imag: "/src/assets/discount__sw-1.png"
      },
    ];

    onMounted(() => {
      // Навигация автоматически привяжется при маунте
    });

    return {
      prevEl,
      nextEl,
      breakpoints,
      products,
      Navigation
    };
  },
};
</script>

<style>
.discount__swiper {
  position: relative;
  height: 350px;
}
.discount__swiper .swiper {
  position: absolute;
  max-width: 1470px;
  height: 100%;
}
.discount__navigation {
  position: absolute;
  top: 50%;
  width: 100%;
  display: flex;
  justify-content: space-between;
  transform: translateY(-50%);
  z-index: 10;
}
.discount__navigation .swiper-button-prev {
  background-image: url(/src/assets/right.svg);
}
.discount__navigation .swiper-button-prev,
.discount__navigation .swiper-button-next {
  background: transparent;
  color: #000;
  border: none;
  cursor: pointer;
  font-size: 24px;
  border-radius: 50%;
}

.discount__content-btn {
  display: block;
  width: 234px;
  margin: 60px auto 0;
}
@media (max-width: 910px) {
  .discount__navigation {
    display: none;
  }
  .discount__swiper .swiper {
    position: absolute;
    max-width: 100%;
    height: 110%;
}
}
</style>
