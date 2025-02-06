<script>
import CategoriesSwiper from "./CategoriesSwiper.vue"; // Имя с большой буквы

export default {
  components: { CategoriesSwiper },
};
</script>

<template>
  <section class="categories">
    <div class="categories__content container">
      <div class="categories__content-body">
        <div class="categories__body-info">
          <p class="categories__info-subtitle subtitle">Categories</p>
          <h2 class="categories__info-title title">Browse By Category</h2>
        </div>
        <!-- Если нужны кнопки навигации, раскомментируй этот блок и добавь refs -->
         
        <div class="categories__navigation">
          <button class="swiper-button-prev" ref="prevBtn">
            <svg width="19" height="16" viewBox="0 0 19 16" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path d="M1.5 8H18M18 8L11 1M18 8L11 15" stroke="black" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
            </svg>
          </button>
          <button class="swiper-button-next" ref="nextBtn">
            <svg width="18" height="16" viewBox="0 0 18 16" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path d="M8 1L1 8L8 15M1 8H17" stroke="black" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
            </svg>
          </button>
        </div>


      </div>
      <CategoriesSwiper />
    </div>
  </section>
</template>

<style scoped>
.categories {
  overflow: hidden;
}
.categories__content-info {
  width: 380px;
}
.categories__content {
  padding: 20px;
}
.categories__navigation {
  display: flex;
  gap: 10px;
  justify-content: center;
  margin-top: 20px;
}
.categories__content-body {
    margin-bottom: 60px;
    position: relative;
    height: 108px;
}
.categories__navigation {
    position: absolute;
    bottom: 20%;
    right: 5%;
}
.swiper-button-prev,
.swiper-button-next {
  background: none;
  border: none;
  cursor: pointer;
}
@media (max-width: 425px) {
  .categories__navigation {
    display: none;
  }
}
</style>
