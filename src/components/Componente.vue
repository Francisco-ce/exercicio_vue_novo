<script setup>
    const props = defineProps(
        ['operacaoMatematica', 'ChamaDoisNumeros', 'ChamaUmNumero',
            'Soma','Subtrai', 'Multiplica', 'Divide', 'Potencia', 'Raiz', 'Fatorial',
            'aaa', 'chamamumeros', 'numero1', 'numero2', 'numero3'
        ])

</script>


<template>

    <h1>
        Calculadora Inteligente
    </h1>
    <h4>Calculadora com dois números</h4>
    <ul @click="props.ChamaDoisNumeros" class="dois_numeros">
        <li @click="props.Soma">Soma</li>
        <li @click="props.Subtrai">Subtração</li>
        <li @click="props.Multiplica">Multiplicação</li>
        <li @click="props.Divide">Divisão</li>
    </ul>
    <h4>Calculadora com um número</h4>
    <ul @click="props.ChamaUmNumero" class="um_numero">
        <li @click="props.Potencia">Pontência</li>
        <li @click="props.Raiz">Raiz Quadrada</li>
        <li @click="props.Fator">Fatorial</li>
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
        {{ props.operacaoMatematica }}
    </span>

</template>