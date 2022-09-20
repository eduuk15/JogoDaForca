<template>
    <div class="teclado">
        <button
            class="teclado-button"
            v-for="(letra, key) in 'abcdefghijklmnopqrtsuvwxyz'"
            :key="key"
            :disabled="verificarLetra(letra)"
            v-on:click="jogar(letra)"
        >
        {{ letra }}
        </button>
    </div>
</template>

<script>

export default {
    name: 'TecladoPage',
    props: {
        letras: Array,
        verificarLetra: Function,
        jogar: Function,
    },
    data() {
    },
    methods: {
    },
    components: {
    }
}
</script>

<style>
    .teclado {
        display: flex;
        flex-wrap: wrap;
        justify-content: center;
        max-width: 85%;
        margin-top: 20px;
    }
    .teclado-button  {
        margin: 5px;
        text-transform: uppercase;
    }
</style>
