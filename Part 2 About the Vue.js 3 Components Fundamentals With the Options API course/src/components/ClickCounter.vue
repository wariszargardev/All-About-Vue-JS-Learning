<script setup>
import { ref } from 'vue'
const count = ref(0)
</script>

<template>
    <h1>Counter {{ count }}</h1>
    <button @click="count++"> Increment </button>
    <button @click="count--"> Decrement </button>
</template>

<style scoped>

</style>

