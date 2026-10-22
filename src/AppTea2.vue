<script setup>
import TeaPlan from './components/TeaPlan.vue';
</script>
<template>
    <div class="content">
        <h1 class="title">Subscripcions disponibles</h1>
        <h2 class="subtitle">
            Disposem dels millor tes del món
        </h2>
        <div class="plans">
            <TeaPlan name="Verds"/>
            <TeaPlan name="Negres"/>
            <TeaPlan name="Vermells"/>
            <TeaPlan name="Blancs"/>
        </div>
    </div>
</template>