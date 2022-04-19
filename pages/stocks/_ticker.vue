<template>
  <div>
    {{ this.stock }}
    <bar-chart />
  </div>
</template>

<script>
import stocks from "~/data/stock-list";
import BarChart from "../../components/BarChart.vue";

export default {
  components: { BarChart },
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
