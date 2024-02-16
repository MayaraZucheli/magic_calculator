<template>
  <div class="calculator">
    <h1 style="font-family: Helvetica, sans-serif; color: #1061a9;">Calculadora mágica</h1>
    <div class="inputs">
      <input type="number" v-model.number="num1" @input="calculate">
      <select v-model="operator" @change="calculate">
        <option value="+">+</option>
        <option value="-">-</option>
        <option value="*">*</option>
        <option value="/">/</option>
      </select>
      <input type="number" v-model.number="num2" @input="calculate">
    </div>
    <h2>Resultado: {{ result }}</h2>
  </div>
</template>

<script>
export default {
  data() {
    return {
      num1: 0,
      num2: 0,
      operator: '+',
      result: 0
    };
  },
  methods: {
    calculate() {
      switch (this.operator) {
        case '+':
          this.result = parseFloat(this.num1) + parseFloat(this.num2);
          break;
        case '-':
          this.result = parseFloat(this.num1) - parseFloat(this.num2);
          break;
        case '*':
          this.result = parseFloat(this.num1) * parseFloat(this.num2);
          break;
        case '/':
          this.result = parseFloat(this.num1) / parseFloat(this.num2);
          break;
        default:
          this.result = 0;
      }
    }
  }
};
</script>

<style>
.calculator {
  max-width: 400px;
  margin: 0 auto;
  padding: 20px;
  border: 1px solid #de5d01;
  border-radius: 8px;
  background-color: #edd310;
}

h1 {
  text-align: center;
}

.inputs {
  display: flex;
  justify-content: center;
  align-items: center;
  margin-bottom: 20px;
}

input, select {
  margin: 0 5px;
  padding: 10px;
  border: 1px solid #de5d01;
  border-radius: 5px;
}

input[type="number"] {
  width: 100px;
}

h2 {
  font-family: Helvetica, sans-serif;
  text-align: center;
  font-size: 24px;
  color: #1061a9;
}
</style>

