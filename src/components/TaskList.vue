
<script setup>
import TaskItem from './TaskItem.vue'

defineProps({
    cartes: {
        type: Array,
        required: true
    }
})

const emit = defineEmits(['canviarEstat', 'eliminarCarta'])

const canviarEstat = (carta) => {
    emit('canviarEstat', carta)
}

const eliminarCarta = (id) => {
    emit('eliminarCarta', id)
}
</script>

<template>

    
    <ul>
        <li v-for="carta in cartes" :key="carta.id">
            {{ carta.nom }} - {{ carta.estat }}

            <button @click="canviarEstat(carta)">
                {{ carta.estat === 'Obtinguda'? 'Marcar pendent': 'Marcar obtinguda' }}
            </button>

            <button @click="eliminarCarta(carta.id)">🗑️</button>
        </li>
    </ul>

    
</template>
