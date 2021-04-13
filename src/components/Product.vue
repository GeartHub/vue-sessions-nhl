<template>
  <v-col cols="12" sm="4" lg="2">
    <v-card elevation="2">
      <v-card-title>{{ product.name }} </v-card-title>
      Price: € {{ price(product.price) }}
      <v-card-actions>
      <v-btn
        outlined
        rounded
        text
        @click="addProductToBasket(product.id)"
      >
        Button
      </v-btn>
    </v-card-actions>
    </v-card>
  </v-col>
</template>

<script>
export default {
  name: "Product",
  props: {
    product: Object
  },
  components: {},
  methods: {
    addProductToBasket(value) {
      this.$emit("productAdded", value)
    },
    price(value) {
      return value.toFixed(2)
    }
  }
};
</script>