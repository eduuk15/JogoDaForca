<template>
    <div class="final">
        <div :class="`final-texto ${etapa}`">
            {{ texto }}
        </div>
        <button
            class="final-button"
            v-on:click="jogarNovamente">
            Jogar Novamente
        </button>
    </div>
</template>

<script>

export default {
    name: 'FinalPage',
    props: {
        etapa: String,
        texto: String,
        jogarNovamente: Function,
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
    .final-texto {
        margin: 20px 0px;
        font-size: 24px;
        font-weight: bold;
    }

    .final-texto.enforcado {
        color: var(--color-text-error);
    }

    .final-texto.ganhador {
        color: var(--color-text-success);
    }
</style>
