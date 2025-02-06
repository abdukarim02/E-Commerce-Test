<template>
    <section class="explore">
        <div class="explore__content container">
            <div class="explore__content-body">
                <div class="explore__body-info info">
                    <p class="explore__info-subtitle subtitle">Our Products</p>
                    <h2 class="explore__info-title title">Explore Our Products</h2>
                </div>
                <div class="explore__navigation">
                    <button class="swiper-button-prev" ref="prevBtn">
                        <svg
                         width="19"
                        height="16"
                        viewBox="0 0 19 16"
                        fill="none"
                        xmlns="http://www.w3.org/2000/svg"
                        >
                        <path
                            d="M1.5 8H18M18 8L11 1M18 8L11 15"
                            stroke="black"
                            stroke-width="1.5"
                            stroke-linecap="round"
                            stroke-linejoin="round"
                        />
                        </svg>
                    </button>
                    <button class="swiper-button-next" ref="nextBtn">
                        <svg
                        width="18"
                        height="16"
                        viewBox="0 0 18 16"
                        fill="none"
                        xmlns="http://www.w3.org/2000/svg"
                        >
                        <path
                            d="M8 1L1 8L8 15M1 8H17"
                            stroke="black"
                            stroke-width="2"
                            stroke-linecap="round"
                            stroke-linejoin="round"
                        />
                        </svg>
                    </button>
                </div>
            </div>
            <div class="explore__content-swiper">
                <swiper
                    :slidesPerView="4"
                    :grid="{ 
                        rows: 2 
                    }"
                    :spaceBetween="30"
                    :modules="modules"
                    class="mySwiper">
                    <swiper-slide v-for="(product, index) in products" :key="index">
                        <DiscountCartList
                            :title="product.title"
                            :price="product.price"
                            :discount="product.discount"
                            :number="product.number"
                            :imag="product.imag"
                            :percent="product.percent"
                        />
                    </swiper-slide>
                    <swiper-slide v-for="(product, index) in products" :key="index">
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
            </div>
        </div>
    </section>
</template>
<style>
.explore {
    margin: 70px 0 140px;
}

.explore__body-info {
    width: 398px;
    margin-bottom: 60px;
}

.explore__info-subtitle {
    width: 142px;
}

.explore__content-body {
    position: relative;
}

.explore__navigation {
    position: absolute;
    right: 5%;
    bottom: 10%;
}

.explore__content-swiper .swiper-wrapper {
    display: flex;
    align-items: center;
    justify-content: space-between;
    flex-direction: row; 
    gap: 30px;
    margin: 0;
}
.explore__content-swiper .swiper-slide {
    margin: 0 !important;
}
@media (max-width: 810px) {
    .explore__content-swiper .swiper-wrapper {
        justify-content: left;
    }
    .explore__content-swiper .swiper-slide {
        width: 30% !important;
    }
}
@media (max-width: 425px) {
    .explore__navigation {
        display: none;
    }
    .explore__content-swiper .swiper-slide {
        width: 60% !important;
    }
    .explore__body-info {
        width: 100%;
    } 
}
</style>
<script>
import { ref } from 'vue';
import DiscountCartList from './DiscountCartList.vue';
import { Swiper, SwiperSlide } from 'swiper/vue';
import 'swiper/css';
import 'swiper/css/grid';
import { Grid, Pagination } from 'swiper/modules';

export default {
    components: {
        Swiper,
        SwiperSlide,
        DiscountCartList,
    },
    setup() {
        const products = ref([
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
        {
            id: 3,
            title: "HAVIT HV-G92 Gamepad",
            price: "$220",
            percent: "-40%",
            discount: "$160",
            number: 88,
            imag: "/src/assets/discount__sw-1.png"
        },
        {
            id: 4,
            title: "HAVIT HV-G92 Gamepad",
            price: "$120",
            percent: "-40%",
            discount: "$160",
            number: 88,
            imag: "/src/assets/discount__sw-1.png"
        },
        {
            id: 5,
            title: "HAVIT HV-G92 Gamepad",
            price: "$220",
            percent: "-40%",
            discount: "$160",
            number: 88,
            imag: "/src/assets/discount__sw-1.png"
        },
        {
            id: 6,
            title: "HAVIT HV-G92 Gamepad",
            price: "$220",
            percent: "-40%",
            discount: "$160",
            number: 88,
            imag: "/src/assets/discount__sw-1.png"
        },
        ]);

        return {
            modules: [Grid, Pagination],
            products,
        };
    },
};
</script>