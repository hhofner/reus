<template>
  <h1>Spent Today: <span :class="{ 'red-negative': spentToday > 0 }">{{ spentToday }}</span></h1>
  <form>
    <div class="dates">
      <input type="date" :value="inputDate"/>
      <input type="time" v-model="inputTime"/>
    </div>
    <div class="priceDetails">
      <input class="price" type="text" inputmode="numeric" placeholder="Price in yen" pattern="[0-9]*"
             v-model="inputPrice"/>
      <div class="select-container">
      <select>
        <option value="">Payment Type</option>
        <option value="cash">Cash</option>
        <option value="paypay">PayPay</option>
        <option value="line-cc">Line Visa</option>
        <option value="mizuho-cc">Mizuho Amex</option>
        <option value="mizuho-db">Mizuho DC</option>
      </select>
      <select>
        <option value="">Category type</option>
        <option value="eat-out">Eat-out</option>
        <option value="groceries">Groceries</option>
        <option value="transportation">Transportation</option>
        <option value="presents">Presents</option>
      </select>
    </div>
    </div>
    <textarea placeholder="Remarks"/>
    <button>Submit</button>
  </form>
</template>

<script setup>
  import { ref } from "vue";

  const spentToday = ref(100);
  const inputDate = ref(null);
  const inputTIme = ref(null);
  const inputPrice = ref(null);
  const inputType = ref(null);
  const inputCategory = ref(null);
  const inputRemarks = ref(null);

  onMounted(() => {
    inputDate.value = new Date()
    console.log(inputDate)
  })
</script>

<script>
export default {
  head:
      {
        meta: {name: "viewport", content: "width=device-width, initial-scale=1, maximum-scale=1"}
      }
};
</script>

<style>
:root {
  box-sizing: border-box;
  font-family: sans-serif;
  --small-spacing: 0.3rem;
  --medium-spacing: 0.6rem;
  --large-spacing: 1rem;
  --very-large-spacing: 2rem;
}

input {
  width:  100%;
  box-sizing: border-box;
}

html {
  max-width: 70ch;
  padding: 3em 1em;
  margin: auto;
  line-height: 1.75;
  font-size: 1.25em;
}

body {
  margin: 0 auto;
}

form {
  gap: var(--very-large-spacing);
  display: flex;
  flex-direction: column;
}

.price {
}

.dates {
  width: 100%;
  display: flex;
  gap: var(--small-spacing);
}

.select-container {
  display: flex;
  justify-content: space-between;
}

.red-negative {
  color: red;
}

@media (max-width: 500px) {
  input, textarea, button {
    font-size: 1.2em;
  }
}

</style>
