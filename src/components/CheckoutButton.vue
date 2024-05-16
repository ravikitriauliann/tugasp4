<template>
  <div class="checkout-button">
    <button @click="checkout">Checkout</button>
  </div>
</template>

<script>
export default {
  name: "CheckoutButton",
  methods: {
    checkout() {
      console.log("Checkout berhasil!");
    },
  },
};
</script>

<style scoped>
.checkout-button {
  text-align: center;
  margin-top: 20px;
}

.checkout-button button {
  background-color: #007bff;
  color: #fff;
  border: none;
  border-radius: 5px;
  padding: 10px 20px;
  cursor: pointer;
  font-size: 18px;
  transition: background-color 0.3s ease;
}

.checkout-button button:hover {
  background-color: #0056b3;
}
</style>
