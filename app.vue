<template>
  <h1>Quick Input</h1>
  <form>
    <input type="date" v-model="inputDate" />
    <input type="time" v-model="inputTime" />
    <div class="priceDetails">
      <label class="price">
        ¥ <input type="number" placeholder="Price" value="inputPrice" />
      </label>
      <select>
        <option value="">Payment Type</option>
        <option value="cash">Cash</option>
        <option value="paypay">PayPay</option>
        <option value="mizuho-cc">Mizuho CC</option>
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
    <textarea placeholder="remarks" />
    <button>Submit</button>
  </form>
</template>

<script>
export default {
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

body {
  max-width: 400px;
  margin: 0 auto;
}

form {
  padding: 0 var(--small-spacing);
  gap: var(--large-spacing);
  display: flex;
  flex-direction: column;
}
</style>
