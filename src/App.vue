<script setup>
import { reactive } from 'vue';
import Cabecalho from './components/Cabecalho.vue'
import Calculos from './components/Formulario.vue'

const estado = reactive({
  valor1: '',
  valor2: '',
  filtro: 'adicao',
});

const adicao = ({ valor1, valor2 } = estado) => {
  return Number(valor1 + valor2);
};
const divisao = ({ valor1, valor2 } = estado) => {
  return valor1 / valor2;
};

const subtracao = ({ valor1, valor2 } = estado) => {
  return valor1 - valor2;
};
const multiplicacao = ({ valor1, valor2 } = estado) => {
  return valor1 * valor2;
};

const calculo = () => {
  const {valor1, valor2, filtro} = estado;

  if ((valor1, valor2)) {
    switch (filtro) {
      case "adicao":
        return adicao();
      case "divisao":
        return divisao();
      case "subtracao":
        return subtracao();
      case "multiplicacao":
        return multiplicacao();
    }
  }
};
</script>

<template>
  <div class="container">
    <Cabecalho />
    <Calculos :valor1="(evento) => (estado.valor1 = Number(evento.target.value))"
              :valor2="(evento) => (estado.valor2 = Number(evento.target.value))"
              :filtro="(evento) => (estado.filtro = evento.target.value)"
              />
      <h2>Resultado: <span>{{ calculo() }}</span></h2>
    
  </div>

</template>

<style scoped>
  h2 {
    text-align: center;
    margin: 20px;
  }
  span {
    color: red;
    text-decoration: underline;
  }
</style>