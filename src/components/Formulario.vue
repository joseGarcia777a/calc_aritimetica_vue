<script setup>
    const props = defineProps(['resultado', 'primeiroDigito', 'segundoDigito', 'exibePrimeiroDigito', 'exibeSegundoDigito', 'trocaOperacao']);
</script>

<template>
    <form class="row centro">
        <input type="number" class="form-control col espaco" :value="props.primeiroDigito" @keyup="props.exibePrimeiroDigito">
        <select name="operacoes" class="col form-control espaco" @change="props.trocaOperacao">
            <option value="escolher" class="text-center">Operação</option>
            <option value="Adicao" class="text-center">( + )</option>
            <option value="Subtracao" class="text-center">( - )</option>
            <option value="Multiplicacao" class="text-center">( * )</option>
            <option value="Divisao" class="text-center">( / )</option>
        </select>
        <input type="number" class="form-control col espaco" :value="props.segundoDigito" @keyup="props.exibeSegundoDigito">
        <p class="col espaco_igual text-center">=</p>
        <p class="form-control col text-center espaco">{{ props.resultado }}</p>
    </form>
</template>

<style scoped>
    .espaco {
        margin: 5px;
    }
    .espaco_igual {
        max-width: 5%;
        align-content: center;
    }
    .centro {
        margin: 0 auto;
        max-width: 70%;
    }
</style>