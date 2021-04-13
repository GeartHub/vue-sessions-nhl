<template>
<v-data-table :headers="headers" :items="items" hide-default-header hide-default-footer></v-data-table>
</template>

<script>
export default {
  name: "Basket",
  props: {
    products: Array,
  },
  data() {
      return {
        headers: [{text: "Product", value: "productName", sortable: false}, {text: "Price", value: "productPrice", sortable: false}],
        items: []
      }
  },
  watch: {
      products() {
          this.items = []
          var totalPrice = 0
          
          for(var index in this.products) {
            //   console.log(this.products[index].price)
              var rowData = {}
              rowData["productName"] = this.products[index].name
              rowData["productPrice"] = "€ " +  this.products[index].price.toFixed(2)
              totalPrice += this.products[index].price
              this.items.push(rowData)
          }
          this.items.push({
              "productName": "Total",
              "productPrice": "€ " +  totalPrice.toFixed(2)
          })
      }
  },
  components: {},
};
</script>