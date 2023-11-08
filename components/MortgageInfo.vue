<template>
  <div class="info animated animatedFadeInUp fadeInUp">
    <div class="info_content">
      <p class="info_label">Узнайте о других <span> интересных предложениях </span></p>
      <h1 class="info_title">Ипотека 0.1%</h1>
      <div class="info_data">
        <div class="info_data-item">
          <span>Ежемесячный платёж</span>
          <p>{{ parseInt(mortgage.monthlyPayment).toLocaleString("ru-Ru") }} ₽</p>
        </div>
        <div class="info_data-item">
          <span>Ставка</span>
          <p>{{ mortgage.rate }}%</p>
        </div>
        <div class="info_data-item">
          <span>Сумма кредита</span>
          <p>{{ parseInt(mortgage.creditAmount).toLocaleString("ru-Ru") }} ₽</p>
        </div>
        <div class="info_data-item">
          <span>Срок кредита</span>
          <p>{{ mortgage.creditTerm }} лет</p>
        </div>
      </div>
    </div>
    <p class="info_text">
      Приведенные расчеты носят предварительный характер. Окончательный расчет суммы кредита и
      размер ежемесячного платежа производится банком после предоставления оценки платежеспособности
      клиента.
    </p>
    <button class="info_btn">Подать заявку на точный расчёт</button>
  </div>
</template>

<script setup>
const mortgage = ref({
  monthlyPayment: 12591,
  rate: 0.1,
  creditAmount: 4465050,
  creditTerm: 5,
});
</script>
<style scoped>
.mainInfo {
  width: 70%;
}
</style>
