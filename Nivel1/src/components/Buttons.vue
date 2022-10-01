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
    }
</style>
