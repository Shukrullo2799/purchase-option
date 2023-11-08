<template>
  <div class="main">
    <Slider />
    <div class="context">
      <MortgageCalculator />
      <MortgageInfo />
    </div>
  </div>
</template>

<script setup></script>
<style scoped>
.main {
  padding: 55px;
  height: 100vh;
  @media screen and (max-width: 1100px) {
    padding: 32px;
  }
  @media (max-width: 768px) {
    padding: 20px;
  }
}
.context {
  display: flex;
  @media (max-width: 1200px) {
    flex-direction: column;
    gap: 20px;
  }
}
</style>
