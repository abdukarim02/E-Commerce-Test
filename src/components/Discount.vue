<script>
import { ref, onMounted, onUnmounted } from "vue";
import DiscountSwiper from "./DiscountSwiper.vue";

export default {
  components: { DiscountSwiper },
  setup() {
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

        Days = Number(Days);
        Hours = Number(Hours);
        Minutes = Number(Minutes);
        Seconds = Number(Seconds);

        if (Seconds > 0) {
          Seconds--;
        } else if (Minutes > 0) {
          Seconds = 59;
          Minutes--;
        } else if (Hours > 0) {
          Seconds = 59;
          Minutes = 59;
          Hours--;
        } else if (Days > 0) {
          Seconds = 59;
          Minutes = 59;
          Hours = 23;
          Days--;
        } else {
          clearInterval(countdownInterval);
          return;
        }

        timeLeft.value = {
          Days: String(Days).padStart(2, "0"),
          Hours: String(Hours).padStart(2, "0"),
          Minutes: String(Minutes).padStart(2, "0"),
          Seconds: String(Seconds).padStart(2, "0"),
        };
      }, 1000);
    };

    onMounted(() => {
      startCountdown();
    });

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
        <DiscountSwiper />
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
  content: "";
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
  width: 100px;
  position: absolute;
  right: 5%;
  top: -10%;
  transform: translateY(-50%);
  background: transparent;
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
.discount__body-watch {
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
  align-items: start;
  flex-direction: column;
  gap: 25px;
}
</style>
