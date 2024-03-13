<script>
export default {
  data() {
    return {
      numero1: 0,
      numero2: 0,
      adicionar: 'add',
      resultado: 0
    };
  },
  methods: {
    calcular() {
      const n1 = parseFloat(this.numero1);
      const n2 = parseFloat(this.numero2);
      switch (this.adicionar) {
        case 'adicao': this.resultado = n1 + n2; break;
        case 'subtracao': this.resultado = n1 - n2; break;
        case 'multiplicacao': this.resultado = n1 * n2; break;
        case 'dividir': this.resultado = (n2 !== 0) ? n1 / n2 : 'Error'; break;
      }
    }
  }
};
</script>

<template>
<div class="container">
  <div>
    <h1>Calculadora</h1>
    <div>
      Digite o primeiro numero: <input type="number" v-model="numero1" @input="calcular" >
    </div>
    <div>
      Digite o segundo numero: <input type="number" v-model="numero2" @input="calcular">
    </div>
    <div>
      Escolha o tipo de calculo:
      <select v-model="adicionar" @change="calcular">
        <option value="adicao">+</option>
        <option value="subtracao">-</option>
        <option value="multiplicacao">*</option>
        <option value="dividir">/</option>
      </select>
    </div>
    <div>
      Resultado final:
      <input class="form-control" type="number" v-model="resultado">
    </div>
  </div>
</div>
</template>

<style scoped>
.container {
  max-width: 400px;
  margin: 0 auto;
  padding: 20px;
  background-color: rgb(150, 127, 98);
  border-radius: 10%;
  color: #fff;
}

h1{
  text-align: center;
  font-size: 64px;
}

input, select {
  margin-bottom: 10px;
  padding: 10px;
  border: 1px solid #ccc;
  border-radius: 5px;
}

input {
  width: 50%;
  background-color: #f9f9f9;
  color: #333;
  font-weight: bold;
  text-align: center;
  border: none;
}

</style>
