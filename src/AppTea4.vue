<script setup>
import {ref} from 'vue'
import PlanPicker from './components/PlanPicker.vue';
const plans = ref(['Verds', 'Negres', 'Vermells', 'Blancs','Variats'])
</script>
<template>
    <div class="content">
        <h1 class="title">Subscripcions disponibles</h1>
        <h2 class="subtitle">
            Disposem dels millor tes del món
        </h2>
    <PlanPicker />
    </div>
</template>