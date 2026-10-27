<script setup>
import TaskForm from './TaskForm.vue'
import { ref } from 'vue'

const nomCarta = ref('')
const estatCarta = ref('')

const gestionarCarta = (nom) => {
    nomCarta.value = nom
    estatCarta.value = 'Nova'
}
</script>

<template>
    
    <div>
        <TaskForm @afegirCarta="gestionarCarta" />

        <p>Nom: {{ nomCarta }}</p>
        <p>Estat: {{ estatCarta }}</p>
    </div>
</template>