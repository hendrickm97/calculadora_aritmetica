<script setup>
const props = defineProps([
  "valorPrimeiroNumero",
  "valorSegundoNumero",
  "filtro",
  "filtroSelecionado",
]);
</script>

<template>
  <form>
    <div class="row mt-5">
      <div class="col-md-4">
        <input
          @keyup="props.valorPrimeiroNumero"
          type="number"
          class="form-control"
          placeholder="Insira o primeiro número"
        />
      </div>
      <div class="col-md-4 text-center">
        <p class="fs-4" v-if="props.filtro === 'soma'">+</p>
        <p class="fs-4" v-else-if="props.filtro === 'subtracao'">-</p>
        <p class="fs-4" v-else-if="props.filtro === 'multiplicacao'">*</p>
        <p class="fs-4" v-else>/</p>
      </div>
      <div class="col-md-4">
        <input
          @keyup="props.valorSegundoNumero"
          type="number"
          class="form-control"
          placeholder="Insira o segundo número"
        />
      </div>
      <div class="col-md-3">
        <select @change="props.filtroSelecionado" class="form-control mt-4">
          <option value="soma">Soma</option>
          <option value="subtracao">Subtração</option>
          <option value="multiplicacao">Multiplicação</option>
          <option value="divisao">Divisão</option>
        </select>
      </div>
    </div>
  </form>
  <template />
</template>
