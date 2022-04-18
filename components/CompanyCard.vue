<template>
  <v-card class="mx-auto" max-width="344" outlined>
    <v-list-item three-line>
      <v-list-item-content>
        <v-list-item-title class="text-h5 mb-1">
          {{ stock.name }}
        </v-list-item-title>
        <v-list-item-subtitle
          >Type:
          {{ this.capitalizeStockType(stock.type) }}</v-list-item-subtitle
        >
      </v-list-item-content>

      <v-list-item-avatar tile size="80" color="grey"></v-list-item-avatar>
    </v-list-item>

    <v-card-actions>
      <v-btn outlined rounded text> {{ stock.symbol }} </v-btn>
    </v-card-actions>
  </v-card>
</template>
<script>
export default {
  props: {
    stock: {
      type: Object,
      required: true,
    },
  },
  methods: {
    capitalizeFirstLetter(string) {
      return string.charAt(0).toUpperCase() + string.slice(1);
    },
    capitalizeStockType(type) {
      return type === "etf"
        ? type.toUpperCase()
        : this.capitalizeFirstLetter(type);
    },
  },
};
</script>
