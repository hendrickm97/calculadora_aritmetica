<script setup>
const props = defineProps([
  "filtro",
  "funcaoSoma",
  "funcaoSubtracao",
  "funcaoMultiplicacao",
  "funcaoDivisao",
]);
</script>

<template>
  <div class="row">
    <div class="col d-flex align-items-center justify-content-center">
      <p>Resultado =</p>
      <div>
        <p v-if="props.filtro === 'soma'">{{ props.funcaoSoma }}</p>
        <p v-else-if="props.filtro === 'subtracao'">
          {{ props.funcaoSubtracao }}
        </p>
        <p v-else-if="props.filtro === 'multiplicacao'">
          {{ props.funcaoMultiplicacao }}
        </p>
        <p v-else>{{ props.funcaoDivisao }}</p>
      </div>
    </div>
  </div>
</template>
