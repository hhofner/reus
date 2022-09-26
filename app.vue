<template>
  <h1>Quick Input</h1>
  <form>
    <div class="dates">
      <input type="date" v-model="inputDate"/>
      <input type="time" v-model="inputTime"/>
    </div>
    <div class="priceDetails">
      <input class="price" type="text" inputmode="numeric" placeholder="Price in yen" pattern="[0-9]*"
             v-model="inputPrice"/>
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
    <textarea placeholder="remarks"/>
    <button>Submit</button>
  </form>
</template>

<script>
export default {
  head:
      {
        meta: {name: "viewport", content: "width=device-width, initial-scale=1, maximum-scale=1"}
      }
  ,
  data() {
    return {
      inputDate: "",
      inputTime: "",
      inputPrice: "",
      inputType: "",
      inputCategory: "",
      inputRemarks: "",
    };
  },
};
</script>

<style>
:root {
  box-sizing: border-box;
  --small-spacing: 0.3rem;
  --medium-spacing: 0.6rem;
  --large-spacing: 1rem;
  --very-large-spacing: 2rem;

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
  gap: var(--large-spacing);
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

@media (max-width: 500px) {
  input, textarea, button {
    font-size: 1.2em;
  }
}

</style>
