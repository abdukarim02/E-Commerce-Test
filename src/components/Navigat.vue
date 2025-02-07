<script>
import { ref } from 'vue';

const searchQuery = ref('');
</script>
<template>
    <header class="header">
      <div class="header__top">
        <div class="container">
          <div class="header__top-content">
            <p class="header__top-text">Summer Sale For All Swim Suits And Free Express Delivery - OFF 50%! <a href="#">ShopNow</a></p>
            <a href="#" class="header__top-translate">English
              <svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path d="M12.364 12.95L17.314 8L18.728 9.414L12.364 15.778L6.00003 9.414L7.41403 8L12.364 12.95Z" fill="white" />
              </svg>
            </a>
          </div>
        </div>
      </div>
      <div class="header__content container">
        <a href="#" class="header__content-logo">Exclusive</a>
        <menu class="header__content-menu">
          <ul class="header__menu-item">
            <li class="header__item-list"><a href="#" class="header__list-link">Home</a></li>
            <li class="header__item-list"><a href="#" class="header__list-link">Contact</a></li>
            <li class="header__item-list"><a href="#" class="header__list-link">About</a></li>
            <li class="header__item-list"><a href="#" class="header__list-link">Sign Up</a></li>
          </ul>
        </menu>
        <div class="header__content-socal">
          <form  id="search" class="header__socal-search">
            <input v-model="searchQuery" class="header__search-input" type="search" placeholder="What are you looking for?">
            <button class="header__search-btn">
              <svg width="18" height="18" viewBox="0 0 18 18" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path d="M17 17L13.2223 13.2156M15.3158 8.15789C15.3158 10.0563 14.5617 11.8769 13.2193 13.2193C11.8769 14.5617 10.0563 15.3158 8.15789 15.3158C6.2595 15.3158 4.43886 14.5617 3.0965 13.2193C1.75413 11.8769 1 10.0563 1 8.15789C1 6.2595 1.75413 4.43886 3.0965 3.0965C4.43886 1.75413 6.2595 1 8.15789 1C10.0563 1 11.8769 1.75413 13.2193 3.0965C14.5617 4.43886 15.3158 6.2595 15.3158 8.15789V8.15789Z" stroke="black" stroke-width="1.5" stroke-linecap="round" />
              </svg>
            </button>
          </form>
          <div class="header__socal-socal">
            <a href="#" class="header__socal-wishlist">
              <svg width="32" height="32" viewBox="0 0 32 32" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path d="M11 7C8.239 7 6 9.216 6 11.95C6 14.157 6.875 19.395 15.488 24.69C15.6423 24.7839 15.8194 24.8335 16 24.8335C16.1806 24.8335 16.3577 24.7839 16.512 24.69C25.125 19.395 26 14.157 26 11.95C26 9.216 23.761 7 21 7C18.239 7 16 10 16 10C16 10 13.761 7 11 7Z" stroke="black" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round" />
              </svg>
            </a>
            <a href="#" class="header__socal-basket">
              <svg width="32" height="32" viewBox="0 0 32 32" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path d="M11 27C11.5523 27 12 26.5523 12 26C12 25.4477 11.5523 25 11 25C10.4477 25 10 25.4477 10 26C10 26.5523 10.4477 27 11 27Z" stroke="black" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round" />
                <path d="M25 27C25.5523 27 26 26.5523 26 26C26 25.4477 25.5523 25 25 25C24.4477 25 24 25.4477 24 26C24 26.5523 24.4477 27 25 27Z" stroke="black" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round" />
                <path d="M3 5H7L10 22H26" stroke="black" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round" />
                <path d="M10 16.6667H25.59C25.7056 16.6667 25.8177 16.6267 25.9072 16.5535C25.9966 16.4802 26.0579 16.3782 26.0806 16.2648L27.8806 7.26479C27.8951 7.19222 27.8934 7.11733 27.8755 7.04552C27.8575 6.97371 27.8239 6.90678 27.7769 6.84956C27.73 6.79234 27.6709 6.74625 27.604 6.71462C27.5371 6.68299 27.464 6.66661 27.39 6.66666H8" stroke="black" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round" />
              </svg>
            </a>
          </div>
        </div>
      </div>
    </header>
</template>
<style scoped>
.header::after {
  content: "";
  display: block;
  width: 100%;
  height: 1px;
  background: #000;
  opacity: 0.3;
}
.header__top {
  padding: 12px 0;
  width: 100%;
  margin: 0 0 0 auto;
  background: #000;
}
.header__top-content {
  display: flex;
  align-items: center;
  justify-content: space-between;
  width: 859px;
  margin-left: auto;
}
.header__top-text {
  font-family: "Inter", sans-serif;
  font-weight: 400;
  font-size: 14px;
  color: #fefaf1;
  line-height: 1.5;
}
.header__top-text a {
  font-family: "Inter", sans-serif;
  font-weight: 600;
  font-size: 14px;
  color: #fefaf1;
  text-decoration: underline;
  -webkit-text-decoration-skip-ink: none;
          text-decoration-skip-ink: none;
  line-height: 1.71429;
}
.header__top-translate {
  font-family: "Inter", sans-serif;
  font-weight: 400;
  font-size: 14px;
  color: #fefaf1;
  width: 78px;
  display: flex;
  align-items: center;
  justify-content: space-between;
}
.header__content {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 40px 20px 16px;
}
.header__content-logo {
  font-family: "Poppins", sans-serif;
  font-weight: 700;
  font-size: 24px;
  color: #000;
  line-height: 1;
  letter-spacing: 0.03em;
}
.header__menu-item {
  width: 367px;
  display: flex;
  align-items: center;
  justify-content: space-between;
}
.header__list-link {
  font-family: "Inter", sans-serif;
  font-weight: 400;
  font-size: 16px;
  color: #000;
  line-height: 1.5;
}
.header__list-link::after {
  content: "";
  display: block;
  width: 0%;
  height: 1px;
  background: #000;
  opacity: 0.5;
  transition: all 0.3s ease-in;
}
.header__list-link:hover::after {
  width: 100%;
}
.header__content-socal {
  width: 347px;
  display: flex;
  align-items: center;
  justify-content: space-between;
}
.header__socal-search {
  width: 211px;
  height: 38px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 7px 12px 7px 20px;
  background: #f5f5f5;
}
.header__search-input {
  padding: 3px 0;
  background: transparent;
}
.header__search-input::-moz-placeholder {
  text-align: center;
  font-family: "Inter", sans-serif;
  font-weight: 400;
  font-size: 12px;
  color: #7d8184;
}
.header__search-input::placeholder {
  text-align: center;
  font-family: "Inter", sans-serif;
  font-weight: 400;
  font-size: 12px;
  color: #7d8184;
}
.header__socal-socal {
  width: 80px;
  display: flex;
  align-items: center;
  justify-content: space-between;
}
@media (max-width: 1024px) {
  .header__top-content {
    width: 100%;
    margin: 0 auto;
  }
}
@media (max-width: 810px) {
  .header__content {
    flex-direction: column;
    gap: 25px;
  }
}
@media (max-width: 768px) {
  .header__top-content {
    flex-direction: column-reverse;
  }
}
@media (max-width: 768px) {
  .header__top-text {
    text-align: center;
  }
  .header__content-socal,
  .header__menu-item {
    flex-direction: column;
    gap: 20px;
  }
  .header__socal-socal,
  .header__socal-search {
    width: 100%;
  }
}
</style>