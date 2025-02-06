<template>
    <div class="discount__card">
        <div class="discount__card-bg">
            <img :src="imag" src="" alt="Product Image" class="discount__bg-img">
            <div class="discount__card-btn">
                <a href="#" class="discount__btn-like">
                    <svg width="18" height="16" viewBox="0 0 18 16" fill="none" xmlns="http://www.w3.org/2000/svg">
                        <path d="M5 1C2.7912 1 1 2.73964 1 4.88594C1 6.61852 1.7 10.7305 8.5904 14.8873C8.71383 14.961 8.85552 15 9 15C9.14448 15 9.28617 14.961 9.4096 14.8873C16.3 10.7305 17 6.61852 17 4.88594C17 2.73964 15.2088 1 13 1C10.7912 1 9 3.35511 9 3.35511C9 3.35511 7.2088 1 5 1Z" stroke="black" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round" />
                    </svg>
                </a>
                <a href="#" class="discount__btn-like">
                    <svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                        <path d="M21.257 10.962C21.731 11.582 21.731 12.419 21.257 13.038C19.764 14.987 16.182 19 12 19C7.81801 19 4.23601 14.987 2.74301 13.038C2.51239 12.7411 2.38721 12.3759 2.38721 12C2.38721 11.6241 2.51239 11.2589 2.74301 10.962C4.23601 9.013 7.81801 5 12 5C16.182 5 19.764 9.013 21.257 10.962V10.962Z" stroke="black" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round" />
                        <path d="M12 15C13.6569 15 15 13.6569 15 12C15 10.3431 13.6569 9 12 9C10.3431 9 9 10.3431 9 12C9 13.6569 10.3431 15 12 15Z" stroke="black" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round" />
                    </svg>
                </a>
            </div>
            <div class="discount__card-percent">
                <p>{{percent}}</p>
            </div>
        </div>
        <div class="discount__card-info">
            <h5 class="discount__info-name">{{ title }}</h5>
            <div class="discount__info-price">
                <span class="discount__price-main">{{ price }}</span>
                <span class="discount__price-discount">{{ discount }}</span>
            </div>
            <div class="discount__info-star">
                <a href="#" class="discount__star-btn">
                    <img src="/src/assets/star.svg" alt="">
                </a>
                <p class="discount__star-number">({{ number }})</p>
            </div>
        </div>
    </div>
</template>

<script setup>
defineProps({
  imag: String,
  title: String,
  price: Number,
  discount: Number,
  percent: Number,
  onClickDelete: Function,
  number: String,
});
</script>
<style setup>
.discount__card {
    width: 100%;
    height: 100%;
}

.discount__card-bg {
    border-radius: 4px;
    width: 100%;
    height: 250px;
    position: relative;
    background: #f5f5f5;
    display: flex;
    align-items: center;
    justify-content: center;
    object-fit: contain;
}
.discount__bg-img {
    width: 172px;
    height: 152px;
    object-fit: contain;
}
.discount__card-btn {
    position: absolute;
    top: 12px;
    right: 12px;
    width: 34px;
    height: 76px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    flex-direction: column;
}
.discount__card-percent {
    position: absolute;
    top: 12px;
    left: 12px;
    border-radius: 4px;
    padding: 4px 12px;
    display: flex;
    align-items: center;
    justify-content: center;
    width: 55px;
    height: 26px;
    font-family: "Poppins", sans-serif;
    font-weight: 400;
    font-size: 12px;
    line-height: 1.5;
    color: #fafafa;
    background: #db4444;
}
.discount__card-info {
    width: 201px;
    height: 84px;
    display: flex;
    align-items: start;
    justify-content: space-between;
    flex-direction: column;
    margin-top: 16px;
}
.discount__info-name {
    font-family: "Poppins", sans-serif;
    font-weight: 500;
    font-size: 16px;
    line-height: 1.5;
    color: #000;
}
.discount__info-price {
    width: 85px;
    display: flex;
    align-items: center;
    justify-content: space-between;
}
.discount__price-main {
    font-weight: 500;
    font-size: 16px;
    line-height: 1.5;
    color: #db4444;
}
.discount__price-discount {
    font-weight: 500;
    font-size: 16px;
    line-height: 1.5;
    text-decoration: line-through;
    color: #000;
    opacity: 0.5;
}
.discount__info-star {
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: space-between;
}
.discount__star-number {
    font-family: "Poppins", sans-serif;
    font-weight: 600;
    font-size: 14px;
    line-height: 1.5;
    color: #000;
    opacity: 0.5;
}

</style>
