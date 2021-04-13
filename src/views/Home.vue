<template>
<v-container>
    <v-row align="center">
    <Product  v-for="(product) of products" :key="product.id" :product="product" @productAdded="productAdded" />
    </v-row>
    <v-row>
      <Basket :products="basket" />
    </v-row>
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
      basket: []
    };
  },
  methods: {
    productAdded(productId) {
      this.basket.push(this.products[productId])
    }
  }
}
</script>
