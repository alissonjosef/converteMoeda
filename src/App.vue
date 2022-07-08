<template>
  <div id="app">
    <h1>Conversor de Moeda</h1>
    <div class="linha">
      <Converte moeda-a="USD" moeda-b="BRL" />
      <Converte moeda-a="BRL" moeda-b="USD" />
    </div>
    <div class="linha">
      <Converte moeda-a="CAD" moeda-b="BRL" />
      <Converte moeda-a="BRL" moeda-b="CAD" />
    </div>
    <div class="linha">
      <Converte moeda-a="EUR" moeda-b="BRL" />
      <Converte moeda-a="BRL" moeda-b="EUR" />
    </div>
  </div>
</template>

<script>
import Converte from "./components/Converte.vue";
export default {
  name: "App",
  components: {
    Converte,
  },
};
</script>

<style>
#app {
  margin: auto;
  max-width: 900px;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.linha{
  margin-top: 40px;
  display: flex;
  justify-content: space-around;
}
</style>
