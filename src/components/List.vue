<template>
  <div>
    <h1>Produkter</h1>
    <ul>
      <li v-for="product in products" :key="product.id">
        {{ product.name }} ({{ product.consumerPrice }})
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "List",
  props: {
    products: Array,
  },
};
</script>

<style scoped></style>
