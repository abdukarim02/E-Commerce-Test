<template>
  <div class="discount__swiper" >

    <swiper
    :slidesPerView="'auto'"
      :spaceBetween="30"
      :breakpoints="breakpoints"
      :modules="modules"
      class="discount__mySwiper"
  >
    <!-- Loop over your products -->
    <swiper-slide v-for="product in products" :key="product.id">
      <DiscountCartList
        :title="product.title"
        :price="product.price"
        :discount="product.discount"
        :number ="product.number"
        :imag="product.imag"
        :percent="product.percent"
      />
    </swiper-slide>
    <swiper-slide v-for="product in products" :key="product.id">
      <DiscountCartList
        :title="product.title"
        :price="product.price"
        :discount="product.discount"
        :number ="product.number"
        :imag="product.imag"
        :percent="product.percent"
      />
    </swiper-slide>
    <swiper-slide v-for="product in products" :key="product.id">
      <DiscountCartList
        :title="product.title"
        :price="product.price"
        :discount="product.discount"
        :number ="product.number"
        :imag="product.imag"
        :percent="product.percent"
      />
    </swiper-slide>
    <swiper-slide v-for="product in products" :key="product.id">
      <DiscountCartList
        :title="product.title"
        :price="product.price"
        :discount="product.discount"
        :number ="product.number"
        :imag="product.imag"
        :percent="product.percent"
      />
    </swiper-slide>
    <swiper-slide v-for="product in products" :key="product.id">
      <DiscountCartList
        :title="product.title"
        :price="product.price"
        :discount="product.discount"
        :number ="product.number"
        :imag="product.imag"
        :percent="product.percent"
      />
    </swiper-slide>

  </swiper>
  </div>


  <a href="#" class="discount__content-btn btn">View All Products</a>
</template>

<script>
import DiscountCartList from './DiscountCartList.vue'
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
    // Breakpoints for responsive design
    const breakpoints = {
      '@0.00': {
        slidesPerView: 1,
        spaceBetween: 10,
      },
      '@0.75': {
        slidesPerView: 2,
        spaceBetween: 20,
      },
      '@1.00': {
        slidesPerView: 3,
        spaceBetween: 40,
      },
      '@1.50': {
        slidesPerView: 4,
        spaceBetween: 50,
      },
    };

    // Sample product data
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
        title: "HAVIT HV-G92 Gamepad",
        price: "$220",
        percent: "-40%",
        discount: "$160",
        number: 88,
        imag: "/src/assets/discount__sw-1.png"
      },
    ];

    return {
      modules: [Navigation],
      breakpoints,
      products,
    };
  },
};
</script>
<style>
.discount__swiper .swiper {
  width: 1470px;
}
.discount__swiper .swiper {
  margin-top: 5%;
}
.discount__swiper .swiper-slide {
  width: 20% !important;
}

@media (max-width: 910px) {

  .discount__navigation {
  display: none;
  }
  .discount__content-btn {
  margin: 60px auto 0;
  }
}


</style>