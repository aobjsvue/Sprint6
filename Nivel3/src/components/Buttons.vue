<script>
    export default {
        name: "Buttons"
    }
</script>

<template>
    <div>
        <button @click="$emit('previousSentence')">Anterior</button>
        <button @click="$emit('nextSentence')">Següent</button>
    </div>
</template>

<style scoped>
    button {
        width: 50%;
        padding: 1.5em 0;
        margin-top: 3.5em;
    }
    @media (min-width: 280px) and (max-width: 480px) {
        button {
            padding: 1em 0;
            margin-top: 3em;
        }
    } 
</style>
