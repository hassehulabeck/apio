<template>
  <div id="app">
    <List :products="products" />
  </div>
</template>

<script>
import List from "./components/List";
import axios from "axios";

export default {
  name: "App",
  components: {
    List,
  },
  data() {
    return {
      url: "https://www.hulabeck.se/hdtml/temp/products.json",
      // Kontrollera alltid din datakälla, helst visuellt.
      products: null,
    };
  },
  mounted() {
    // När ska du hämta data?
    axios
      .get(this.url)
      .then((response) => {
        this.products = response.data.products;
      })
      .catch((error) => {
        console.error("Fel:" + error);
      })
      .then(() => {
        console.log("Körs alltid");
      });
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
