<template>
  <div id="app" class="container mt-5">
    <h1 class="mb-5">Calculadora Aritmética</h1>
    <div class="row">
      <div class="col-md-4">
        <label for="numero1">Número 1:</label>
        <input v-model="numero1" @input="calcularResultado" type="number" class="form-control">
      </div>
      <div class="col-md-4">
        <label for="operacao">Operação:</label>
        <select v-model="operacao" @change="calcularResultado" class="form-select">
          <option value="soma">Soma</option>
          <option value="subtracao">Subtração</option>
          <option value="multiplicacao">Multiplicação</option>
          <option value="divisao">Divisão</option>
        </select>
      </div>
      <div class="col-md-4">
        <label for="numero2">Número 2:</label>
        <input v-model="numero2" @input="calcularResultado" type="number" class="form-control">
      </div>
    </div>
    <div class="mt-4">
      <h3>Resultado: {{ resultado }}</h3>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      numero1: 0,
      numero2: 0,
      operacao: 'soma',
      resultado: 0,
    };
  },
  methods: {
    calcularResultado() {
      const num1 = parseFloat(this.numero1);
      const num2 = parseFloat(this.numero2);

      switch (this.operacao) {
        case 'soma':
          this.resultado = num1 + num2;
          break;
        case 'subtracao':
          this.resultado = num1 - num2;
          break;
        case 'multiplicacao':
          this.resultado = num1 * num2;
          break;
        case 'divisao':
          this.resultado = num2 !== 0 ? num1 / num2 : 'Indefinido';
          break;
        default:
          this.resultado = 0;
      }
    },
  },
};
</script>

<style>

</style>