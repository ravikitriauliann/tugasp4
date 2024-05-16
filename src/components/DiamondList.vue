<template>
  <div class="diamond-list">
    <h2 class="diamond-title">
      Daftar Harga Promo Top-up Diamond Mobile Legends
    </h2>
    <ul>
      <li v-for="diamond in diamonds" :key="diamond.id" class="diamond-item">
        <span class="diamond-name">{{ diamond.name }}</span>
        <span class="diamond-price">Rp.{{ formatPrice(diamond.price) }},-</span>
        <button @click="selectDiamond(diamond)" class="buy-button">Beli</button>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "DiamondList",
  data() {
    return {
      diamonds: [
        {
          id: 1,
          name: "Promo 1 (53 + 6 Bonus) Total 59 Diamonds",
          price: 15200,
        },
        {
          id: 2,
          name: "Promo 2 (77 + 8 Bonus) Total 85 Diamonds",
          price: 21850,
        },
        {
          id: 3,
          name: "Promo 3 (154 + 16 Bonus) Total 170 Diamonds",
          price: 43700,
        },
        {
          id: 4,
          name: "Promo 4 (217 + 23 Bonus) Total 240 Diamonds",
          price: 61750,
        },
        {
          id: 5,
          name: "Promo 5 (256 + 40 Bonus) Total 296 Diamonds",
          price: 76000,
        },
        {
          id: 6,
          name: "Promo 6 (367 + 41 Bonus) Total 408 Diamonds",
          price: 104500,
        },
        {
          id: 7,
          name: "Promo 7 (503 + 65 Bonus) Total 296 Diamonds",
          price: 142500,
        },
        {
          id: 8,
          name: "Promo 8 (774 + 101 Bonus) Total 875 Diamonds",
          price: 218500,
        },
        {
          id: 9,
          name: "Promo 9 (1708 + 302 Bonus) Total 2010 Diamonds",
          price: 475000,
        },
        {
          id: 10,
          name: "Promo 10 (4003 + 837 Bonus) Total 4830 Diamonds",
          price: 1140000,
        },
      ],
    };
  },
  methods: {
    selectDiamond(diamond) {
      this.$emit("diamond-selected", diamond);
    },
    formatPrice(price) {
      return price.toLocaleString("id-ID");
    },
  },
};
</script>

<style scoped>
.diamond-list {
  background-color: #4d7192;
  border-radius: 10px;
  padding: 20px;
}

.diamond-title {
  font-size: 24px;
  color: #fff;
  margin-bottom: 20px;
}

.diamond-item {
  list-style: none;
  margin-bottom: 10px;
  padding: 10px;
  background-color: #797979;
  border-radius: 5px;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.3);
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.diamond-name,
.diamond-price {
  color: #fff;
}

.buy-button {
  background-color: #007bff;
  color: #fff;
  border: none;
  border-radius: 5px;
  padding: 5px 10px;
  cursor: pointer;
  transition: background-color 0.3s ease;
}

.buy-button:hover {
  background-color: #0056b3;
}
</style>
