<template>
  <div class="calc animated animatedFadeInUp fadeInUp">
    <button class="calc-btn">Ипотечный калькулятор</button>
    <div class="calc-content">
      <div>
        <label class="calc-label" for="price">Стоимость, млн ₽</label>
        <div class="calc-data flex justify-content-between">
          <div class="w-6 relative">
            <div class="calc-data_price">
              <span>{{ form.price }}</span>
            </div>
            <input
              class="calc-data_range-left"
              type="range"
              v-model="form.price"
              min="1"
              max="10"
              step="0.1"
            />
          </div>
          <div>|</div>

          <div class="w-6 relative flex justify-content-end">
            <div>
              <span>{{ form.price2 }}</span>
            </div>
            <input
              class="calc-data_range-right"
              type="range"
              v-model="form.price2"
              min="1"
              max="10"
              step="0.1"
            />
          </div>
        </div>
      </div>
      <div class="calc-checks">
        <div class="flex align-items-center">
          <input class="calc-check" type="checkbox" v-model="form.home" />
          <label class="calc-label mb-0" for="home">Квартира</label>
        </div>
        <div class="flex align-items-center">
          <input class="calc-check" type="checkbox" v-model="form.apartment" />
          <label class="calc-label mb-0" for="apartment">Апартамент</label>
        </div>
      </div>
      <div>
        <label class="calc-label" for="down_payment">Первоначальный взнос, ₽</label>
        <div class="calc-data">
          <div class="calc-data_price">
            <span>
              {{ parseInt(maxPrice * (form.down_persent / 100)).toLocaleString("ru-RU") }}
            </span>
            <span>{{ form.down_persent }} </span>
          </div>
          <input class="calc-data_range" type="range" v-model="form.down_persent" />
        </div>
      </div>
      <div>
        <label class="calc-label" for="credit_term">Срок выплат</label>
        <div class="calc-data">
          <div class="calc-data_price">
            <span>{{ Math.round(form.credit_term / 12) }} лет </span>
          </div>
          <input
            class="calc-data_range"
            type="range"
            v-model="form.credit_term"
            max="180"
            min="12"
          />
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
const maxPrice = 5000000;
const form = ref({
  price: 5.6,
  price2: 5.6,
  home: false,
  apartment: false,
  down_persent: 20,
  credit_term: 60,
});
form.value.down_payment = parseInt(maxPrice * (form.value.down_persent / 100));
</script>
