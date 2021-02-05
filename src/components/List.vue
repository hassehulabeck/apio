<template>
  <div>
    <h1>ECBs växelkurser</h1>
    <ul>
      <h2>{{ ratesobject.base }}</h2>
      <p>{{ ratesobject.date }}</p>
      <li v-for="(currency, rate, index) of ratesobject.rates" :key="index">
        En {{ ratesobject.base }} kostar {{ currency }} {{ rate }} .
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "List",
  props: {
    ratesobject: Object,
  },
};
</script>

<style scoped></style>
