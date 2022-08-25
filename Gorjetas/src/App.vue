<script>
export default {
  data() {
    return {
      valorConta: 0,
      Gorjeta: 15,
      numPessoas: 1,
    };
  },
  methods: {
    calcular() {
      const valorConta = this.valorConta;
      const Gorjeta = this.Gorjeta;
      const numPessoas = this.numPessoas;
      let valorGorjeta = 0;
      let valorTotal = {};

      valorGorjeta = valorConta * (Gorjeta / 100);
      valorTotal = (valorConta + valorGorjeta) / numPessoas;

      valorTotal = Math.round(valorTotal * 100) / 100;
      valorTotal = valorTotal.toFixed(2);

      console.log(valorTotal);

      document.getElementById("resultado").innerHTML = valorTotal;

    }
  }
};


</script>

<template>

  <div class="main">

    <h1><strong>Calcular Gorjetas</strong></h1>

    <form>

      <label>
        <p>Qual o valor do jantar?</p>
        <input type="number" v-model="valorConta" id="valorConta">
      </label>

      <label>
        <p>Qual a porcentagem gorjeta?</p>
        <select v-model="Gorjeta" id="valorGorjeta">
          <option value="30">30% Excelente serviço</option>
          <option value="25">25% Muito bom</option>
          <option value="20">20% Bom</option>
          <option value="15">15% Aceitável</option>
          <option value="10">10% Ruim</option>
          <option value="5">5% "Péssimo"</option>
        </select>
      </label>

      <label>
        <p>Quantas pessoas vão dividir a conta?</p>
        <input v-model="numPessoas" type="number" id="numPessoas">
      </label>

      <label>
        <p>Calcular:</p>
        <button type="button" @click="calcular">R$:<span id="resultado">0.00</span></button>
      </label>

    </form>

  </div>

</template>

<style scoped>
.main {
  position: absolute;
  background-color: rgb(217, 185, 244);
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  text-align: center;
  padding: 25px;
  border-radius: 5px;
 border: solid 2px #7a13b9;
}
h1 {
  font-size: 30px;
  color:#6b2aa0;
}
p{
  color:#6e4cb3;
}
input,
select {
  margin-bottom: 30px;
}
input,
select,
button {
  width: 250px;
  height: 25px;
  font-size: 18px;
  border: 2px rgb(90, 3, 221) solid;
  border-radius: 2px;
  text-align: center;
  transition: 0.25s;
  cursor: pointer;
}
button {
  background-color: #7a13b9;
  height: 50px;
  font-size: 24px;
  margin-bottom: 10px;
}
button:hover {
  background-color: #9369c4;
}
</style>