<!-- Código JavaScript -->

<script setup>
import { reactive } from 'vue';
import Componente from './components/Componente.vue'


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
  <Componente :operacao-matematica="operacaoMatematica()" :-chama-um-numero="ChamaUmNumero()" 
  :-chama-dois-numeros="ChamaDoisNumeros()" :-soma="Soma()" :-subtrai="Subtrai()" :-divide="Divide()" 
  :-raiz="Raiz()" :-potencia="Potencia()" :-fatorial="Fator()" :-multiplica="Multiplica()" :aaa="estado.aaa" :chamamumeros="estado.chamanumeros" 
  :numero1="estado.numero1", :numero2="estado.numero2" :numero3="estado.numero3" />
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
