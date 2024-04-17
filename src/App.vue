<script setup>
import { reactive } from 'vue';
import Calculadora from "./components/Calculadora.vue"

  const estado = reactive({
    num1: 0,
    num2: 0,
    resultado: 0
  })

  const mudaResultado = operador => {
    const { num1, num2 } = estado

    switch (operador) {
      case "subtracao":
        estado.resultado =  num1 - num2
      case "multi":
        estado.resultado =  num1 * num2
      case "divisao":
        if(num2!=0){
          estado.resultado =  num1 / num2
        } else {
          alert("Não se pode dividir por 0")
          estado.resultado = 0
          return
        }
      case "soma":
        estado.resultado =  num1 + num2
        console.log(estado.resultado)
      default:
        return
    }
    
  }
</script>

<template>
  <div class="container">
    <div class="row text-center my-4">
      <h1>Calculadora VueJS</h1>
    </div>
    <div class="row mt-4 mb-4 align-content-center">
      <Calculadora :define-num1="evento => estado.num1 = parseInt(evento.target.value)" :define-num2="evento => estado.num2 = parseInt(evento.target.value)" :muda-resultado="evento => mudaResultado(evento.target.value)" />
    </div>
    <div class="text-center fs-2">
      Resultado: <br>
      {{ estado.resultado }}
    </div>
  </div>
</template>
