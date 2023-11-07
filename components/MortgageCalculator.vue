<template>
  <div class="calc">
    <button class="calc-btn">Ипотечный калькулятор</button>
    <div>
      <label for="price">Стоимость недвижимости</label>
      <div>
        <div>
          <input type="range" id="price" name="price" min="1000000" max="10000000" />
          <input type="text" id="price" name="price" />
        </div>
        <div>
          <input type="range" id="price2" name="price2" min="1000000" max="10000000" />
          <input type="text" id="price2" name="price2" />
        </div>
      </div>
    </div>
    <div>
      <input type="checkbox" v-model="form.home" />
      <label for="home">Квартира</label>
      <input type="checkbox" v-model="form.apartment" />
      <label for="apartment">Апартамент</label>
    </div>
    <div>
      <label for="down_payment">Первоначальный взнос, ₽</label>
      <div>
        <div>
          <span>
            {{ parseInt(maxPrice * (form.down_persent / 100)).toLocaleString("ru-RU") }}
          </span>
          <span>{{ form.down_persent }} </span>
        </div>
        <input type="range" v-model="form.down_persent" />
      </div>
      <div>
        <label for="credit_term">Срок выплат</label>
        <div>
          <span>{{ Math.round(form.credit_term / 12) }} лет </span>
          <input type="range" v-model="form.credit_term" max="180" min="12" />
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
