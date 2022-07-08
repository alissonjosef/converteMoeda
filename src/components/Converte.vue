<template>
  <div class="conversor">
    <div>
      <h2>{{ moedaA }} para {{ moedaB }}</h2>
      <input type="text" v-model="moedaA_value" v-bind:placeholder="moedaA" />
      <input type="button" value="Converter" v-on:click="converter" />
      <h2>{{ moedaB_value }}</h2>
    </div>
  </div>
</template>

<script>
export default {
  name: ["converte"],
  props: ["moedaA", "moedaB"],
  data() {
    return {
      moedaA_value: "",
      moedaB_value: 0,
    };
  },
  methods: {
    converter() {
      let de_para = this.moedaA + "-" + this.moedaB;
      let str = de_para.replace("-", "");
      let url = `https://economia.awesomeapi.com.br/json/last/${de_para}`;

      fetch(url)
        .then((res) => {
          return res.json();
        })
        .then((json) => {
          let contacao = json[str].ask;
          console.log(contacao);
          this.moedaB_value = (
            contacao * parseFloat(this.moedaA_value)
          ).toFixed(2);
        });
    },
  },
};
</script>

<style scoped>
.conversor {
  padding: 20px;
  max-width: 300px;
  box-shadow: 0px 4px 8px 0px rgba(0, 0, 0, 0.2);
}
</style>