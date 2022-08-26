<script>
export default {
  data() {
    return {
      people: "",
      count: "",
      valor_gorjeta: "",
  }},
  methods: {
    calcular(){
      const people = this.people;
      const count = this.count;
      const valor_gorjeta = this.valor_gorjeta;

      let valor_valor_gorjeta = 0;
      let resultado = {};

      valor_valor_gorjeta = count * (valor_gorjeta / 100);
      resultado = (count + valor_valor_gorjeta) / people;
      resultado = Math.round(resultado);
      document.getElementById("resultado").innerHTML = resultado;
    }
  },
};
</script>

<template>
<body>
  <main>
  <div class="conteudo-oi">
    <h1>Gorjetas de Gotham</h1>
    <label> <p>Qual o valor da conta?</p>
      <input type="number" v-model="count" id="conta">
    </label>

    <label>
      <p>Qual foi a qualidade do serviço?</p>
      <select oi v-model="valor_gorjeta">
        <option value="100">100% THE JOKER</option>
        <option value="50">50% O alto escalão de Gotham</option>
        <option value="30">30% Excepcional</option>
        <option value="25">25% Muito bom</option>
        <option value="20">20% Bom</option>
        <option value="15">15% Ok</option>
        <option value="10">10% Ruim</option>
        <option value="5">5% Péssimo</option>
      </select>
    </label>

    <label><p>Quantas pessoas estão dividindo a conta?</p>
      <input type="number" v-model="people" id="people">
    </label>
    <p>Gorjeta do Garçon</p>
    <button type="button" @click="calcular">R$:
      <span id="resultado"></span>
    </button>
    <h2>É do restaurante direto pro ARKHAN</h2>
  </div>
  </main>
</body>
</template>