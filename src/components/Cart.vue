<template>
  <div class="cart">
    <h2 class="cart-title">Keranjang Belanja</h2>
    <ul>
      <li v-for="item in cartItems" :key="item.id" class="cart-item">
        <span class="cart-item-name">{{ item.name }}</span> -
        <span class="cart-item-price">Rp.{{ formatPrice(item.price) }},-</span>
      </li>
    </ul>
    <p v-if="cartItems.length === 0" class="empty-cart-message">
      Keranjang belanja kosong.
    </p>
    <p v-else class="total-price">
      Total Harga: Rp.{{ formatPrice(totalCartPrice) }},-
    </p>
  </div>
</template>

<script>
export default {
  name: "Cart",
  props: {
    cartItems: Array,
  },
  computed: {
    totalCartPrice() {
      return this.cartItems.reduce((total, item) => total + item.price, 0);
    },
  },
  methods: {
    formatPrice(price) {
      return price.toLocaleString("id-ID");
    },
  },
};
</script>

<style scoped>
.cart {
  background-color: #4d7192;
  border-radius: 10px;
  padding: 20px;
}

.cart-title {
  font-size: 24px;
  color: #fff;
  margin-bottom: 20px;
}

.cart-item {
  list-style: none;
  margin-bottom: 10px;
  padding: 10px;
  background-color: #35985e;
  border-radius: 5px;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.3);
}

.cart-item-name,
.cart-item-price {
  color: #fff;
}

.empty-cart-message {
  color: #fff;
  font-size: 14px;
}

.total-price {
  color: #fff;
  font-size: 18px;
  margin-top: 10px;
}
</style>
