<script setup>
//import TaskList from './components/TaskApp.vue';

import { ref, computed } from 'vue'
import '../public/styles.css'

import TaskForm from './components/TaskForm.vue';
import TaskList from './components/TaskList.vue';


const mostrarPendents = ref(false)
const cartaNova = ref('')

// Array on es guarden les cartes
const cartes = ref([
  { id: 1, nom: 'Pikachu', estat: 'Obtinguda' },
  { id: 2, nom: 'Charizard', estat: 'Pendent' },
  { id: 3, nom: 'Greninja', estat: 'Pendent' }
])

const cartesPendents = computed(() => {
  if (mostrarPendents.value) {
    return cartes.value.filter(carta => carta.estat === 'Pendent')
  }
  return cartes.value 
})

const totalCartes = computed(() => cartes.value.length)
const totalPendents = computed(() => cartes.value.filter(carta => carta.estat === 'Pendent').length)

// Funció per afegir una carta nova a l'array de cartes
function afegirCarta(nom) {
  if (nom.trim() === '') return

  const nova = {
    id: Date.now(),
    nom: nom,
    estat: 'Pendent'
  }

  cartes.value.push(nova)
}
// Funció per canviar l'estat d'una carta entre 'Obtinguda' i 'Pendent'
function canviarEstat(carta) {
  carta.estat = carta.estat === 'Obtinguda' ? 'Pendent' : 'Obtinguda'
}

// Funció per eliminar una carta de l'array de cartes
function eliminarCarta(id) {
  cartes.value = cartes.value.filter(carta => carta.id !== id)
}

</script>


<template>
  <h1>Gestor de Cartes</h1>

  <TaskForm
  @afegirCarta="afegirCarta">
  </TaskForm>

  <label>
    <input type="checkbox" v-model="mostrarPendents" /> Mostrar només cartes pendents
  </label>

  <TaskList
    :cartes="cartes"
    @canviarEstat="canviarEstat"
    @eliminarCarta="eliminarCarta"
  />
  
</template>
