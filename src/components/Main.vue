<template>
    <section class="main">
      <div class="main__content container">
        <div class="main__content-bar">
          <menu class="main__bar-menu">
            <ul class="main__menu-item">
              <li class="main__item-list">
                <a href="#" class="main__list-link">
                  Woman’s Fashion
                  <svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                    <path d="M12.95 11.636L8 6.68597L9.414 5.27197L15.778 11.636L9.414 18L8 16.586L12.95 11.636Z" fill="black" />
                  </svg>
                </a>
              </li>
              <li class="main__item-list">
                <a href="#" class="main__list-link">
                  Men’s Fashion
                  <svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                    <path d="M12.95 11.636L8 6.68597L9.414 5.27197L15.778 11.636L9.414 18L8 16.586L12.95 11.636Z" fill="black" />
                  </svg>
                </a>
              </li>
              <li class="main__item-list"><a href="#" class="main__list-link">Electronics</a></li>
              <li class="main__item-list"><a href="#" class="main__list-link">Home & Lifestyle</a></li>
              <li class="main__item-list"><a href="#" class="main__list-link">Medicine</a></li>
              <li class="main__item-list"><a href="#" class="main__list-link">Sports & Outdoor</a></li>
              <li class="main__item-list"><a href="#" class="main__list-link">Baby’s & Toys</a></li>
              <li class="main__item-list"><a href="#" class="main__list-link">Groceries & Pets</a></li>
              <li class="main__item-list"><a href="#" class="main__list-link">Health & Beauty</a></li>
            </ul>
          </menu>
        </div>
        <div class="main__content-swiper">
            <swiper :spaceBetween="0" :centeredSlides="true" :autoplay="{  delay: 2500,  disableOnInteraction: false, }" :pagination="{ clickable: true,  }" :navigation="true" :modules="modules"  class="mySwiper">
                <swiper-slide>
                    <div class="main__swiper-info">
                        <a href="#" class="main__info-logo">
                            <img src="/src/assets/swiper-logo.svg" alt="">
                            <p>iPhone 14 Series</p>
                        </a>
                        <p class="main__info-title">Up to 10% off Voucher</p>
                        <a href="#" class="main__info-btn">Shop Now
                            <svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                                <path d="M3.5 12H20M20 12L13 5M20 12L13 19" stroke="#FAFAFA" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round" />
                            </svg>
                        </a>
                    </div>
                    <div class="main__swiper-bg">
                        <img src="/src/assets/swiper-bg.jpg" alt="">
                    </div>
                </swiper-slide>
                <swiper-slide>
                    <div class="main__swiper-info">
                        <a href="#" class="main__info-logo">
                            <img src="/src/assets/swiper-logo.svg" alt="">
                            <p>iPhone 14 Series</p>
                        </a>
                        <p class="main__info-title">Up to 10% off Voucher</p>
                        <a href="#" class="main__info-btn">Shop Now
                            <svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                                <path d="M3.5 12H20M20 12L13 5M20 12L13 19" stroke="#FAFAFA" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round" />
                            </svg>
                        </a>
                    </div>
                    <div class="main__swiper-bg">
                        <img src="/src/assets/swiper-bg.jpg" alt="">
                    </div>
                </swiper-slide>
            </swiper>
        </div>
      </div>
    </section>
</template> 
<script>
  // Import Swiper Vue.js components
  import { Swiper, SwiperSlide } from 'swiper/vue';
  // Import Swiper styles
  import 'swiper/css';
  import 'swiper/css/pagination';
  import 'swiper/css/navigation';

  // import required modules
  import { Autoplay, Pagination, Navigation } from 'swiper/modules';

  export default {
    components: {
      Swiper,
      SwiperSlide,
    },
    setup() {
      return {
        modules: [Autoplay, Pagination, Navigation],
      };
    },
  };
</script>
<style>
.main__content {
  width: 100%;
  overflow: hidden;
  display: flex;
  align-items: start;
  justify-content: space-between;
  gap: 45px;
}
.main__content-bar {
  padding: 40px 16px 0 0;
  flex: 0 1 20%;
  position: relative;
  z-index: 1;
}
.main__content-bar::after {
  content: "";
  display: block;
  position: absolute;
  top: 0;
  right: 0;
  width: 100%;
  height: 110%;
  border-right: 0.5px solid #000;
  opacity: 0.3;
  z-index: 0;
}
.main__menu-item {
  height: 344px;
  display: flex;
  align-items: start;
  justify-content: space-between;
  flex-direction: column;
}
.main__item-list {
  width: 100%;
  position: relative;
  z-index: 2;
}
.main__list-link {
  width: 100%;
  display: flex;
  align-items: center;
  justify-content: space-between;
  font-family: "Inter", sans-serif;
  font-weight: 400;
  font-size: 16px;
  color: #000;
}
.main__content-swiper {
  margin: 40px auto 0;
  flex: 0 1 80%;
  height: 100%;
  background: #000;
}
.main__content-swiper .swiper-slide {
  padding: 16px 0;
  display: flex;
  align-items: center;
  justify-content: space-between;
}
.swiper-pagination-bullet {
  width: 12px;
  height: 12px;
  background: #7d8184;
  transition: all 0.3s ease-in;
}
.swiper-pagination-bullet-active {
  background: #db4444;
}
.main__swiper-info {
  width: 294px;
  margin: 0 auto;
}
.main__info-logo {
  width: 190px;
  display: flex;
  align-items: center;
  justify-content: space-between;
}
.main__info-logo p {
  font-family: "Poppins", sans-serif;
  font-weight: 400;
  font-size: 16px;
  color: #fafafa;
}
.main__info-title {
  margin: 20px 0 22px;
  font-family: "Inter", sans-serif;
  font-weight: 600;
  font-size: 48px;
  color: #f5f5f5;
}
.main__info-btn {
  width: 113px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  font-family: "Inter", sans-serif;
  font-weight: 600;
  font-size: 16px;
  color: #f5f5f5;
  position: relative;
  line-height: 1.5;
  text-align: center;
  padding-bottom: 5px;
}
.main__info-btn::after {
  content: "";
  position: absolute;
  bottom: 0;
  left: 0;
  display: block;
  width: 70%;
  height: 1px;
  background: #fafafa;
}
.main__swiper-bg {
  width: 50%;
  height: 344px;
}
.main__swiper-bg img {
  width: 100%;
  height: 100%;
  -o-object-fit: contain;
     object-fit: contain;
}
.main__content .swiper-slide {
  width: 100% !important;
  height: 100% !important;
}
.main__content .swiper-button-prev,
.main__content .swiper-button-next{
    display: none !important;
}
@media (max-width: 1024px) {
  .main__content-bar {
    flex: 0 1 30%;
  }
  .main__content-swiper {
    flex: 0 1 70%;
  }
}
@media (max-width: 910px) {
  .main__content {
    gap: 25px;
  }
  .main__content-swiper {
    width: 100%;
    flex: 0 1 46%;
  }
  .main__content-bar {
    flex: 0 1 46%;
  }
}
@media (max-width: 810px) {
  .main__content {
    flex-direction: column;
  }
  .main__content-bar {
    flex: 0 1 100%;
    width: 100%;
  }
  .main__menu-item {
    flex-direction: unset;
    flex-wrap: wrap;
  }
  .main__item-list {
    flex: 0 1 30%;
  }
  .main__list-link {
    width: 100%;
  }
  .main__content-bar::after {
    border-right: none;
    border-bottom: 1px solid #000;
  }
}
@media (max-width: 425px) {
  .main__item-list {
    flex: 0 1 47%;
  }
  .main__content-swiper .swiper-slide {
    flex-direction: column;
    align-items: start;
    padding: 20px;
  } 
  .main__swiper-info {
    margin: 0;
  }
  .main__swiper-bg {
    width: 100%;
  }
  .jbl-boombox__info-title {
    font-size: 35px !important;
    margin: 25px 0 !important;
  }
}
</style>