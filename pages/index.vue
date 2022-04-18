<template>
  <div>
    <v-container class="grey lighten-5">
      <v-row no-gutters>
        <v-col
          v-for="stock in stocks"
          :key="stock.symbol"
          cols="12"
          sm="4"
          style="padding: 10px"
        >
          <company-card :stock="stock"></company-card>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>

<script>
import stocks from "~/data/stock-list";
import CompanyCard from "~/components/CompanyCard.vue";

export default {
  components: {
    CompanyCard,
  },
  data() {
    return {
      stocks: stocks.slice(0, 100),
    };
  },
};
</script>

<style lang=""></style>
