<template>
  <div
    class="slider_item animated animatedFadeInUp fadeInUp"
    :style="{
      backgroundImage: `url(/${item.img}.png)`,
    }"
  >
    <p class="slider_item-title">{{ item.title }}</p>
    <p class="slider_item-text">
      {{ item.text }}
    </p>
    <span class="slider_item-btn">
      <svg
        xmlns="http://www.w3.org/2000/svg"
        width="65"
        height="66"
        viewBox="0 0 65 66"
        fill="none"
      >
        <circle cx="32.5" cy="33.3125" r="32.5" fill="#083E4C" />
        <path
          d="M40.3889 33.1687C41.0556 33.5536 41.0556 34.5158 40.3889 34.9007L30.3889 40.6742C29.7222 41.0591 28.8889 40.578 28.8889 39.8082L28.8889 28.2612C28.8889 27.4914 29.7222 27.0103 30.3889 27.3952L40.3889 33.1687Z"
          fill="white"
        />
      </svg>
    </span>
  </div>
</template>

<script setup>
const { item } = defineProps({
  item: {
    type: Object,
    default: () => ({}),
  },
});
</script>
