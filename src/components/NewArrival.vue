<template>
    <section class="arrival">
        <div class="arrival__content container">
            <div class="arrival__content-info info">
                <p class="arrival__info-subtitle subtitle">Featured</p>
                <h2 class=" title">New Arrival</h2>
            </div>
            <div class="arrival__content-body">
                <div class="arrival__body-wrap">
                    <div class="arrival__wrap-flex">
                        <div class="arrival__flex-body">
                            <div class="arrival__body-bg">
                                <img src="/src/assets/NewArrival-bg-1.png" alt="">
                            </div>
                            <div class="arrival__body-info">
                                <h5 class="arrival__info-title">PlayStation 5</h5>
                                <p class="arrival__info-text">Black and White version of the PS5 coming out on sale.</p>
                                <a href="#" class="arrival__info-btn">Shop Now</a>
                            </div>
                        </div>
                    </div>
                    <div class="arrival__wrap-flex">
                        <div class="arrival__flex-body top">
                            <div class="arrival__body-bg">
                                <img src="/src/assets/NewArrival-bg-2.png" alt="">
                            </div>
                            <div class="arrival__body-info">
                                <h5 class="arrival__info-title">PlayStation 5</h5>
                                <p class="arrival__info-text">Black and White version of the PS5 coming out on sale.</p>
                                <a href="#" class="arrival__info-btn">Shop Now</a>
                            </div>
                        </div>
                        <div class="arrival__flex-body footer">
                            <div class="arrival__flex-body">
                                <div class="arrival__body-bg">
                                    <img src="/src/assets/NewArrival-bg-3.png" alt="">
                                </div>
                                <div class="arrival__body-info">
                                    <h5 class="arrival__info-title">PlayStation 5</h5>
                                    <p class="arrival__info-text">Black and White version of the PS5 coming out on sale.</p>
                                    <a href="#" class="arrival__info-btn">Shop Now</a>
                                </div>
                            </div>
                            <div class="arrival__flex-body">
                                <div class="arrival__body-bg">
                                    <img src="/src/assets/NewArrival-bg-4.png" alt="">
                                </div>
                                <div class="arrival__body-info">
                                    <h5 class="arrival__info-title">PlayStation 5</h5>
                                    <p class="arrival__info-text">Black and White version of the PS5 coming out on sale.</p>
                                    <a href="#" class="arrival__info-btn">Shop Now</a>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>
<style setup>
.arrival__content-info  {
    margin-bottom: 60px;
}
.arrival__body-wrap {
    display: flex;
    align-items: center;
    justify-content: space-between;
    flex-wrap: wrap;
}
.arrival__wrap-flex {
    flex: 0 1 48%;
    width: 100%;
    height: 600px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    flex-direction: column;
}
.arrival__flex-body {
    width: 100%;
    height: 600px;
    position: relative;
    z-index: 1;
}
.arrival__body-bg {
    position: absolute;
    width: 100%;
    height: 100%;
    top: 0;
    z-index: 0;
    cursor: pointer;
    overflow: hidden;
}
.arrival__body-bg:hover.arrival__body-bg img:hover {
    transform: scale(1.2);
}
.arrival__body-bg img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    transform: scale(1);
    transition: all 0.3s ease;
}
.arrival__body-info {
    width: 40%;
    height: 122px;
    display: flex;
    align-items: start;
    justify-content: space-between;
    flex-direction: column;
    position: absolute;
    z-index: 2;
    left: 32px;
    bottom: 32px;
}
.arrival__info-title {
    font-family: "Inter", sans-serif;
    font-weight: 600;
    font-size: 24px;
    line-height: 1;
    letter-spacing: 0.03em;
    color: #fafafa;
}
.arrival__info-text {
    font-weight: 400;
    font-size: 14px;
    line-height: 1.5;
    color: #fafafa;
}
.arrival__info-btn {
    font-weight: 500;
    font-size: 16px;
    line-height: 1.5;
    color: #fff;
}
.top {
    height: 284px;
}
.arrival .footer {
    height: 284px;
    display: flex;
    align-items: center;
    justify-content: space-between;
}
.arrival .footer .arrival__flex-body {
    width: 47%;
    height: 284px;
}
.arrival .footer .arrival__body-info {
    width: 80%;
    height: 100px
}
@media (max-width: 768px) {
.arrival__body-wrap {
    flex-direction: column;
    gap: 25px;
}
.arrival__wrap-flex {
    gap: 25px;
}

} 
@media (max-width: 425px) {
    .arrival__flex-body {
        height: 450px;
    }
    .arrival .footer {
        width: 100%;
        height: 100%;
        align-items: start;
        flex-direction: column;
        gap: 25px;

    }
    .arrival .footer .arrival__flex-body {
        width: 100%;
        height: 450px;
    }
}
</style>