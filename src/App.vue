<script setup>
import { reactive } from "vue";
import Cabecalho from "./components/Header.vue";
import Formulario from "./components/Form.vue";
import Resultado from "./components/Result.vue";

const estado = reactive({
  filtro: "soma",
  num1: "",
  num2: "",
  resultado: "",
});

const soma = () => {
  const resultadoDaSoma = estado.num1 + estado.num2;
  estado.resultado = resultadoDaSoma;
  return estado.resultado;
};
const subtracao = () => {
  const resultadoDaSubtracao = estado.num1 - estado.num2;
  estado.resultado = resultadoDaSubtracao;
  return estado.resultado;
};
const multiplicacao = () => {
  const resultadoDaMultiplicacao = estado.num1 * estado.num2;
  estado.resultado = resultadoDaMultiplicacao;
  return estado.resultado;
};
const divisao = () => {
  const resultadoDaDivisao = estado.num1 / estado.num2;
  estado.resultado = resultadoDaDivisao;
  return estado.resultado;
};
</script>

<template>
  <div class="container">
    <Cabecalho />
    <Formulario
      :valorPrimeiroNumero="
        (event) => (estado.num1 = Number(event.target.value))
      "
      :valorSegundoNumero="
        (event) => (estado.num2 = Number(event.target.value))
      "
      :filtro="estado.filtro"
      :filtroSelecionado="(event) => (estado.filtro = event.target.value)"
    />
    <Resultado
      :filtro="estado.filtro"
      :funcaoSoma="soma()"
      :funcaoSubtracao="subtracao()"
      :funcaoMultiplicacao="multiplicacao()"
      :funcaoDivisao="divisao()"
    />
  </div>
</template>

<style scoped>
.container {
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
}
</style>
