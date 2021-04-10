<template>
  <v-col cols="12" sm="4" lg="2">
    <v-card elevation="2">
      <v-card-title>{{ name }} </v-card-title>
      Price: €{{ price }}
    </v-card>
  </v-col>
</template>

<script>
export default {
  name: "Home",
  props: {
    name: String,
    price: String,
  },
  components: {},
};
</script>