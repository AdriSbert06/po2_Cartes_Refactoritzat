<script setup>
import { ref } from 'vue'

const cartaNova = ref('')
const emit = defineEmits(['afegirCarta'])

const afegirCarta = () => {
    if (cartaNova.value.trim() === '') return

    emit('afegirCarta', cartaNova.value)
    cartaNova.value = ''
}
</script>

<template>
    <input
        v-model="cartaNova"
        type="text"
        placeholder="Introdueix la carta"
    />
    <button @click="afegirCarta">Afegir</button>
</template>