<template>
<v-container>
    <v-row align="center">
    <Product  v-for="(product) of products" :key="product" :name="product.name" :price="product.price" />
    </v-row>
</v-container>
</template>

<script>
// @ is an alias to /src
import Product from "../components/Product.vue"

export default {
  name: 'Home',
  components: {
    Product
  },
  data() {
    return {
      products: [
        {
          name: "Pizza pepperoni",
          price: "8,00"
        },
        {
          name: "7up",
          price: "1,50"
        }
      ]
    };
  },
}
</script>
