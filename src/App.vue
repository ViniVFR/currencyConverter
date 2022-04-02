<template>
  <div id="app">
    <h1 class="text-center">Currency Converter</h1>

    <div class="row">
      <wConverter
        currencyA="BRL"
        currencyB="USD"
      />
      <wConverter
        currencyA="USD"
        currencyB="BRL"
      />
    </div>

    <div class="row">
      <wConverter
        currencyA="BRL"
        currencyB="CAD"
      />
      <wConverter
        currencyA="CAD"
        currencyB="BRL"
      />
    </div>
    
    <div class="row">
      <wConverter
        currencyA="BRL"
        currencyB="EUR"
      />
      <wConverter
        currencyA="EUR"
        currencyB="BRL"
      />
    </div>
  </div>
</template>


<script>
import wConverter from "./components/w-Converter.vue";
export default {
  name: 'App',
  components: {
    wConverter
  }
}
</script>

<style>
#app {
  margin: auto;
  max-width: 900px;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}
.row {
  margin-top: 40px;
  display: flex;
  justify-content: space-around;
}
.text-center {
  text-align: center;
}
</style>
