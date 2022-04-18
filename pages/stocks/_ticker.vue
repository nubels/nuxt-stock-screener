<template>
  <div>{{ this.stock }}</div>
</template>

<script>
import stocks from "~/data/stock-list";

export default {
  data() {
    return {
      stock: {},
    };
  },
  created() {
    const ticker = this.$route.params.ticker.toUpperCase();
    const stock = stocks.find((stock) => stock.symbol === ticker);
    this.stock = stock;
  },
};
</script>
