<template>
<v-container>
    <v-row align="center">
    <Product  v-for="(product) of products" :key="product.id" :product="product" @productAdded="productAdded" />
    </v-row>
    <v-row>
      <Basket :products="basket" />
    </v-row>
    <v-snackbar
      v-model="snackbar"
    >
      {{ snackbarText }}

      <template v-slot:action="{ attrs }">
        <v-btn
          color="pink"
          text
          v-bind="attrs"
          @click="snackbar = false"
        >
          Close
        </v-btn>
      </template>
    </v-snackbar>
</v-container>
</template>

<script>
// @ is an alias to /src
import Product from "../components/Product.vue"
import Basket from "../components/Basket.vue"

export default {
  name: 'Home',
  components: {
    Product,
    Basket
  },
  data() {
    return {
      products: [
        {
          name: "Pizza pepperoni",
          price: 8.00,
          id: 0
        },
        {
          name: "7up",
          price: 1.50,
          id: 1
        }
      ],
      basket: [],
      snackbar: false,
      snackbarText: ""
    };
  },
  methods: {
    productAdded(productId) {
      this.snackbar = true
      this.snackbarText = this.products[productId].name + " has been added to your basket"
      this.basket.push(this.products[productId])
    }
  }
}
</script>
