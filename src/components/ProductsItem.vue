<script>
import { ref } from "vue";
import DiscountCartList from "./DiscountCartList.vue";

export default {
  components: { DiscountCartList },
  setup() {
    const products = ref([
      {
        id: 1,
        title: "HAVIT HV-G92 Gamepad",
        price: "$120",
        percent: "-40%",
        discount: "$160",
        number: 88,
        imag: "/src/assets/discount__sw-1.png",
      },
      {
        id: 2,
        title: "HAVIT HV-G92 Gamepad",
        price: "$220",
        percent: "-40%",
        discount: "$160",
        number: 88,
        imag: "/src/assets/discount__sw-1.png",
      },
      {
        id: 3,
        title: "HAVIT HV-G92 Gamepad",
        price: "$120",
        percent: "-40%",
        discount: "$160",
        number: 88,
        imag: "/src/assets/discount__sw-1.png",
      },
      {
        id: 4,
        title: "HAVIT HV-G92 Gamepad",
        price: "$220",
        percent: "-40%",
        discount: "$160",
        number: 88,
        imag: "/src/assets/discount__sw-1.png",
      },
    ]);

    return { products };
  },
};
</script>

<template>
  <section class="best-product">
    <div class="best-product__content container">
      <div class="best-product__content-body">
        <div class="best-product__body-info">
          <p class="best-product__info-subtitle subtitle">This Month</p>
          <h2 class="best-product__info-title title">Best Selling Products</h2>
        </div>
        <a href="#" class="best-product__content-btn btn">View All</a>
      </div>
      <div class="best-product__content-wrap">
        <DiscountCartList
          v-for="product in products"
          :key="product.id"
          :title="product.title"
          :price="product.price"
          :discount="product.discount"
          :number="product.number"
          :imag="product.imag"
          :percent="product.percent"
        />
      </div>
    </div>
  </section>
</template>

<style scoped>
.best-product {
    margin: 60px 0 150px;
}
.best-product__content-body {
    display: flex;
    align-items: center;
    justify-content: space-between;
}
.best-product__info-subtitle {
    width: 125px;
    margin-bottom: 20px;
}
.best-product__content-wrap {
  display: flex;
  gap: 20px;
  flex-wrap: wrap;
  align-items: center;
  justify-content: space-between;
  margin-top: 60px;
}
.best-product__content-wrap .discount__card {
    width: 23%;
    height: auto;
}
@media (max-width: 810px) {
  .best-product__content-wrap .discount__card {
    width: 30%;
  }
}
@media (max-width: 425px) {
  .best-product__content-wrap .discount__card {
    width: 100%;
  }
  .best-product__content-body {
    flex-direction: column;
    align-items: start;
    gap: 25px;
  }
}
</style>
