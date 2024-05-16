<template>
  <div class="app-container">
    <h1 class="app-title">TOP UP MURAH DAN TRPERCAYA HANYA DI Aulian.store</h1>
    <diamond-list @diamond-selected="addToCart"></diamond-list>
    <cart :cart-items="cartItems"></cart>
  </div>
</template>

<script>
import DiamondList from "./components/DiamondList.vue";
import Cart from "./components/Cart.vue";

export default {
  name: "App",
  components: {
    DiamondList,
    Cart,
  },
  data() {
    return {
      cartItems: [],
    };
  },
  methods: {
    addToCart(diamond) {
      this.cartItems.push(diamond);
    },
  },
};
</script>

<style scoped>
.app-container {
  max-width: 800px;
  margin: 0 auto;
  padding: 20px;
}

.app-title {
  font-size: 36px;
  color: #fff;
  text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5);
}
</style>
