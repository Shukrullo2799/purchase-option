<template>
  <div class="slider">
    <div class="slider_header">
      <p class="slider_header-title">Варианты покупки</p>
      <div class="slider_actions">
        <button class="slider_actions-info">Подробнее</button>
        <div class="slider_actions-arrows">
          <button class="slider_actions-arrows-left">
            <svg
              xmlns="http://www.w3.org/2000/svg"
              width="62"
              height="62"
              viewBox="0 0 62 62"
              fill="none"
            >
              <g>
                <path
                  d="M1 30.8125C1 47.381 14.4315 60.8125 31 60.8125C47.5685 60.8125 61 47.381 61 30.8125C61 14.244 47.5685 0.8125 31 0.8125C14.4315 0.8125 1 14.244 1 30.8125Z"
                  stroke="#083E4C"
                />
                <path
                  class="arrow"
                  d="M26.5 29.9465C25.8333 30.3314 25.8333 31.2936 26.5 31.6785L32.5 35.1426C33.1667 35.5275 34 35.0464 34 34.2766L34 27.3484C34 26.5786 33.1667 26.0975 32.5 26.4824L26.5 29.9465Z"
                  fill="#083E4C"
                />
              </g>
            </svg>
          </button>
          <button class="slider_actions-arrows-right">
            <svg
              xmlns="http://www.w3.org/2000/svg"
              width="62"
              height="62"
              viewBox="0 0 62 62"
              fill="none"
            >
              <g>
                <path
                  d="M61 30.8125C61 47.381 47.5685 60.8125 31 60.8125C14.4315 60.8125 1 47.381 1 30.8125C1 14.244 14.4315 0.8125 31 0.8125C47.5685 0.8125 61 14.244 61 30.8125Z"
                  stroke="#083E4C"
                />
                <path
                  class="arrow"
                  d="M35.5 29.9465C36.1667 30.3314 36.1667 31.2936 35.5 31.6785L29.5 35.1426C28.8333 35.5275 28 35.0464 28 34.2766L28 27.3484C28 26.5786 28.8333 26.0975 29.5 26.4824L35.5 29.9465Z"
                  fill="#083E4C"
                />
              </g>
            </svg>
          </button>
        </div>
      </div>
    </div>
    <Swiper
      class="swiper"
      :slides-per-view="3"
      :space-between="30"
      :loop="true"
      :effect="'creative'"
      :autoplay="{
        delay: 8000,
        disableOnInteraction: true,
      }"
      :creative-effect="{
        prev: {
          shadow: false,
          translate: ['-20%', 0, -1],
        },
        next: {
          translate: ['100%', 0, 0],
        },
      }"
      :navigation="{
        prevEl: '.slider_actions-arrows-left',
        nextEl: '.slider_actions-arrows-right',
      }"
      @navigationNext="console.log('next')"
    >
      <SwiperSlide v-for="(slide, i) in data" :key="i">
        <SliderCard :item="slide" />
      </SwiperSlide>
    </Swiper>
  </div>
</template>

<script setup>
const data = ref([
  {
    img: 1,
    title: "Ипотека от 4,3%",
    text: "Выгодные условия при оформлении у банков-партнеров",
  },
  {
    img: 2,
    title: "Рассрочка 0%",
    text: "Гибкие условия по размеру первоначального взноса, платежам и срокам",
  },
  {
    img: 3,
    title: "Покупка в Trade-in",
    text: "Выгодный обмен старой квартиры на новую квартиру или апартаменты",
  },
  {
    img: 1,
    title: "Ипотека от 4,3%",
    text: "Выгодные условия при оформлении у банков-партнеров",
  },
  {
    img: 2,
    title: "Рассрочка 0%",
    text: "Гибкие условия по размеру первоначального взноса, платежам и срокам",
  },
  {
    img: 3,
    title: "Покупка в Trade-in",
    text: "Выгодный обмен старой квартиры на новую квартиру или апартаменты",
  },
]);
</script>
