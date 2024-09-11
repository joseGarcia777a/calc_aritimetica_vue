<script setup>
  import Formulario from './components/Formulario.vue';
  import {reactive} from 'vue';

  const estado = reactive({
    digitoUm: '',
    digitoDois: '',
    troca: 'Escolher'
  });

  const getMultiplica = () => {
    const result = estado.digitoDois * estado.digitoUm;
    return result;
  };

  const getDivide = () => {
    const result = estado.digitoUm / estado.digitoDois;
    return result;
  };

  const getSubtrai = () => {
    const result = estado.digitoUm - estado.digitoDois;
    return result;
  };

  const getSoma = () => {
    const result = estado.digitoUm - - estado.digitoDois;
    return result;
  };

  const getTrocaOperacao = () => {
    const troca = estado.troca;

    switch(troca){
      case 'Adicao':
        return getSoma();
      case 'Subtracao':
        return getSubtrai();
      case 'Multiplicacao':
        return getMultiplica();
      case 'Divisao':
        return getDivide();
      default:
        return estado.troca;
    };
  };

</script>

<template>
  <body>
    <header>
      <div class="container text-bg-secondary p-5 mb-4 rounded-3">
        <h1>Calculadora</h1>
        <h3>VUE.js</h3>
      </div>
    </header>
    <div class="container">
      <Formulario 
      :primeiro-digito="estado.digitoUm"
      :segundo-digito="estado.digitoDois" 
      :exibe-primeiro-digito="evento => estado.digitoUm = evento.target.value"
      :exibe-segundo-digito="evento => estado.digitoDois = evento.target.value"
      :troca-operacao="evento => estado.troca = evento.target.value"
      :resultado="getTrocaOperacao()" 
      />
    </div>
  </body>
</template>

<style scoped>

</style>
