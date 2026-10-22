<script setup>
import {ref} from 'vue'
import TeaPlan from './components/TeaPlan.vue';
const plans = ref(['Verds', 'Negres', 'Vermells', 'Blancs','Variats'])
</script>
<template>
    <div class="content">
        <h1 class="title">Subscripcions disponibles</h1>
        <h2 class="subtitle">
            Disposem dels millor tes del món
        </h2>
        <div class="plans">
            <TeaPlan v-for="plan in plans" :key="plan" :name="plan"/>
            
        </div>
    </div>
</template>