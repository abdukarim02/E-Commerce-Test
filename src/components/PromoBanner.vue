<template>
    <section class="jbl-boombox">
        <div class="container">
            <div class="jbl-boombox__content ">
              <div class="jbl-boombox__content-info">
                <p class="jbl-boombox__info-subtitle">Категории</p>
                <h2 class="jbl-boombox__info-title">Усильте свой музыкальный опыт</h2>
                <div class="jbl-boombox__body-watch">
                  <div
                    class="jbl-boombox__watch-numbers"
                    v-for="(value, key) in timeLeft"
                    :key="key">
                    <span>{{ value }}</span>
                    <p class="jbl-boombox__numbers-name">{{ key }}</p>
                  </div>
                </div>
                <a href="#" class="jbl-boombox__info-btn btn">Купить сейчас!</a>
              </div>
              <div class="jbl-boombox__content-bg">
                <img src="/src/assets/jbl_boomBox.png" alt="JBL BoomBox">
              </div>
            </div>
        </div>
    </section>
</template>
<script>
  import { ref, onMounted } from 'vue';
  
  export default {
    setup() {
      const timeLeft = ref({
        Hours: "23",
        Days: "05",
        Minutes: "59",
        Seconds: "35",
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
      });
  
      return {
        timeLeft
      };
    }
  }
</script>
<style setup>
.jbl-boombox__content {
    padding: 38px 45px;
    background: #000;
    display: flex;
    align-items: center;
    justify-content: space-between;
}
.jbl-boombox__info-subtitle {
    font-family: "Poppins", sans-serif;
    font-weight: 600;
    font-size: 16px;
    line-height: 1.25;
    color: #0f6;
}
.jbl-boombox__info-title {
    font-family: "Inter", sans-serif;
    font-weight: 600;
    font-size: 48px;
    line-height: 1.25;
    letter-spacing: 0.04em;
    margin: 32px 0;
    color: #fafafa;
}
.jbl-boombox__body-watch {
    width: 320px;
    height: 62px;
    margin-bottom: 55px;
    display: flex;
    align-items: center;
    justify-content: space-between;
}
.jbl-boombox__watch-numbers {
    width: 62px;
    height: 62px;
    border-radius: 100%;
    background: #fff;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
}
.jbl-boombox__watch-numbers span {
    font-family: "Poppins", sans-serif;
    font-weight: 600;
    font-size: 16px;
    line-height: 1.25;
    color: #000;
}
.jbl-boombox__numbers-name {
    font-family: "Poppins", sans-serif;
    font-weight: 400;
    font-size: 11px;
    line-height: 1.63636;
    color: #000;
}
.jbl-boombox__info-btn {
    background: #0f6;
}
.jbl-boombox__content-bg {
    width: 50%;
    height: 420px;
}
.jbl-boombox__content-bg img {
    width: 100%;
    height: 100%;
    object-fit: contain;
}
@media (max-width: 425px) {
  .jbl-boombox__content {
    flex-direction: column;
    align-items: start;
  }
  .jbl-boombox__body-watch {
    width: 100%;
  }
  .jbl-boombox__content-bg {
    width: 100%;
  }
}
</style>
  