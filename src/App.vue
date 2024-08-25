<!-- Código JavaScript -->

<script setup>
import { reactive } from 'vue';



//constantes e objetos//

const estado = reactive({
  numero1: 0,
  numero2: 0,
  numero3: 0,
  auxiliar:'',
  resultado1: 0,
  resultado2: 0,
  chamanumeros: false,
  aaa: false
})

  const pessoa = {
    nome: 'Francisco',
    sobrenome: 'Corrêa',
    idade: 34,
    profissao: 'engenheiro'
  }



  // Funções//
// function usuario(){
//   return `Usuário: ${pessoa.nome} ${pessoa.sobrenome}, ${pessoa.idade} anos, ${pessoa.profissao}`
// }

function Soma() {
  return estado.auxiliar = 'soma' 
}

function Subtrai() {
  return estado.auxiliar = 'subtrai'
}

function Multiplica() {
  return estado.auxiliar = 'multiplica'
}

function Divide() {
  return estado.auxiliar = 'divide'
}

function Raiz() {
  return estado.auxiliar = 'raiz'
}

function Potencia() {
  return estado.auxiliar = 'potencia'
}

function Fator() {
  return estado.auxiliar = 'fator'
}

function ChamaDoisNumeros() {
  return estado.chamanumeros = true, estado.aaa = false
}

function ChamaUmNumero() {
  return estado.chamanumeros = false, estado.aaa = true
}

function calculaFator() {
  const num = estado.numero3
  let numFator = 1
  for (let i=1; i <= num; i++) {
    numFator *= i
  }
  return numFator
}

function operacaoMatematica() {
  const {auxiliar, numero1, numero2, numero3} = estado

  switch(auxiliar) {
    case 'soma':
      return numero1 + numero2
    case 'subtrai':
      return numero1 - numero2
    case 'multiplica':
      return numero1 * numero2
    case 'divide':
      return numero1 / numero2
    case 'potencia': 
      return numero3**2
    case 'raiz':
      return numero3**(1/2)
    case 'fator':
      return calculaFator()
    default:
      return ''
  }
}

</script>

<template>
<div class="container">
  <h1>
        Calculadora Inteligente
    </h1>
    <h4>Calculadora com dois números</h4>
    <ul @click="ChamaDoisNumeros" class="dois_numeros">
        <li @click="Soma">Soma</li>
        <li @click="Subtrai">Subtração</li>
        <li @click="Multiplica">Multiplicação</li>
        <li @click="Divide">Divisão</li>
    </ul>
    <h4>Calculadora com um número</h4>
    <ul @click="ChamaUmNumero" class="um_numero">
        <li @click="Potencia">Pontência</li>
        <li @click="Raiz">Raiz Quadrada</li>
        <li @click="Fator">Fatorial</li>
    </ul>
    <div class="container-inputs">
        <div v-if="estado.chamanumeros" class="container-numero-2">
            <label for="">Número 1:</label>
            <input type="number" @keyup="evento => estado.numero1 = parseFloat(evento.target.value)"
                placeholder="Digite um número">
            <label for="">Número 2:</label>
            <input type="number" @keyup="evento => estado.numero2 = parseFloat(evento.target.value)"
                placeholder="Digite um número">
        </div>
        <div v-if="estado.aaa" class="container-numero-1">
            <label for="">Número:</label>
            <input type="number" @keyup="evento => estado.numero3 = parseFloat(evento.target.value)"
                placeholder="Digite um número">
        </div>
    </div>
    <span>
        {{ operacaoMatematica() }}
    </span>
</div>


</template>

<style scoped>

* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

.container {
  padding: 30px;
  text-align: center;
  display: block;
}

.dois_numeros{
  display: grid;
  grid-template-columns: 1fr 1fr 1fr 1fr;
  gap: 5px;
  list-style: none;
  cursor: pointer;
}

.um_numero{
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  gap: 5px;
  list-style: none;
  cursor: pointer;
  
}

li {
  padding: 5px;
  border: 1px black solid;
  border-radius: 10px;
}



</style>
