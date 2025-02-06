<script>
import { ref, onMounted, onUnmounted } from "vue";
import DiscountSwiper from "./DiscountSwiper.vue";

export default {
  components: { DiscountSwiper },
  setup() {
    const prevBtn = ref(null);
    const nextBtn = ref(null);
    const timeLeft = ref({
      Days: "07",
      Hours: "23",
      Minutes: "19",
      Seconds: "56",
    });

    let countdownInterval = null;

    const startCountdown = () => {
      countdownInterval = setInterval(() => {
        let { Days, Hours, Minutes, Seconds } = timeLeft.value;
        Days = parseInt(Days);
        Hours = parseInt(Hours);
        Minutes = parseInt(Minutes);
        Seconds = parseInt(Seconds);

        if (Seconds > 0) {
          Seconds--;
        } else {
          Seconds = 59;
          if (Minutes > 0) {
            Minutes--;
          } else {
            Minutes = 59;
            if (Hours > 0) {
              Hours--;
            } else {
              Hours = 23;
              if (Days > 0) {
                Days--;
              } else {
                clearInterval(countdownInterval);
              }
            }
          }
        }

        timeLeft.value = {
          Days: Days.toString().padStart(2, "0"),
          Hours: Hours.toString().padStart(2, "0"),
          Minutes: Minutes.toString().padStart(2, "0"),
          Seconds: Seconds.toString().padStart(2, "0"),
        };
      }, 1000);
    };

    onMounted(() => {
      startCountdown();
      console.log("Swiper navigation elements initialized:", prevBtn.value, nextBtn.value);
    });
    return { prevBtn, nextBtn, timeLeft };

    onUnmounted(() => {
      clearInterval(countdownInterval);
    });

    return { timeLeft };
  },
};
</script>
<template>
 <section class="discount">
    <div class="discount__content">
      <div class="container">
        <div class="discount__content-body">
          <div class="discount__body-info info">
            <p class="discount__info-subtitle subtitle">Today’s</p>
            <h2 class="discount__info-title title">Flash Sales</h2>
          </div>
          <div class="discount__body-watch">
            <div
              class="discount__watch-numbers"
              v-for="(value, key) in timeLeft"
              :key="key"
            >
              <p class="discount__numbers-name">{{ key }}</p>
              <span>{{ value }}</span>
            </div>
          </div>
        </div>

        <div class="discount__navigation">
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

        <DiscountSwiper :prevEl="prevBtn" :nextEl="nextBtn" />
      </div>
    </div>
  </section>
</template>
<style>
.discount {
    overflow: hidden;
    margin: 140px 0;
}
.discount__content .container::after {
    content: '';
    width: 100%;
    height: 100%;
    display: block;
    padding-bottom: 60px; 
    border-bottom: 1px solid #000;
    opacity: 0.5;
}
.discount__content .container {
    position: relative;
}
.discount__navigation {
    position: absolute;
    right: 5%;
    top: 10%;
    transform: translateY(-50%);
}
.swiper-button-prev,
.swiper-button-next {
    width: 24px;
    height: 24px;
} 
.swiper-button-prev svg,
.swiper-button-next svg {
    width: 100%;
    height: 100%;
    object-fit: contain;
}
.swiper-button-prev::after, 
.swiper-button-next::after {
    display: none;
}
.discount__content-body {
    width: 600px;
    height: 103px;
    display: flex;
    align-items: end;
    justify-content: space-between;  
    margin-bottom: 40px;
}
.discount__body-watch{
    width: 302px;
    display: flex;
    align-items: center;
    justify-content: space-between;

}
.discount__watch-numbers {
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: space-between;
    flex-direction: column;
}
.discount__numbers-name {
    font-family: "Poppins", sans-serif;
    font-weight: 500;
    font-size: 12px;
    line-height: 1.5;
    color: #000;
}
.discount__watch-numbers span {
    font-weight: 700;
    font-size: 32px;
    line-height: 0.9375;
    letter-spacing: 0.04em;
    color: #000;
}
.discount__content-body {
    height: 100%;
    align-items: start ;
    flex-direction: column;
    gap: 25px;
  }
</style>