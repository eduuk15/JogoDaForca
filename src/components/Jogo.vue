<template>
    <div class="jogo">

        <Forca
            :erros="erros"
        />

        <Palavra
            :palavra="palavra"
            :dica="dica"
            :verificarLetra="verificarLetra"
            :etapa="etapa"
        />

        <Teclado
        v-if="etapa === 'jogo'"
            :letras="letras"
            :verificarLetra="verificarLetra"
            :jogar="jogar"
        />

        <Final
        v-if="etapa != 'jogo'"
            :etapa="etapa"
            :texto="etapa == 'ganhador' ? 'Parabéns!!! Você acertou :)' : 'Seu tanso!!! ERROUUU :('"
            :jogarNovamente="jogarNovamente"
        />

    </div>
</template>

<script>

import Forca from './Forca.vue'
import Palavra from './Palavra.vue'
import Teclado from './Teclado.vue'
import Final from './Final'

export default {
    name: 'JogoPage',
    props: {
        erros: Number,
        palavra: String,
        dica: String,
        verificarLetra: Function,
        etapa: String,
        letras: Array,
        jogar: Function,
        jogarNovamente: Function,
    },
    data() {
    },
    methods: {
    },
    components: {
        Forca,
        Palavra,
        Teclado,
        Final
    }
}
</script>

<style>

.jogo {
    width: 100%;
    display: flex;
    flex-direction: column;
    align-items: center;
    text-align: center;
}
</style>
