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
         


      </div>
      <CategoriesSwiper />
    </div>
  </section>
</template>

<style scoped>
.categories {
}
.categories__content-info {
  width: 380px;
}
.categories__content {
  position: relative;
  padding: 20px;
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
