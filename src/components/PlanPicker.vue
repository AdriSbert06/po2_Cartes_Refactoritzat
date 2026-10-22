<script setup>
import {ref} from 'vue'
import TeaPlan2 from './TeaPlan2.vue'
const plans =ref(['Verds','Negres','Vermells','Blancs','Variats'])
const selectedTeaPlan=ref()
function gestioTeaPlan(name){
    selectedTeaPlan.value=name
}
</script>
<template>
    <div class="plans">
        {{ selectedTeaPlan }}
        <TeaPlan2 v-for="plan in plans" 
                 :key="plan" 
                 :name="plan" 
                 :selected="plan===selectedTeaPlan" 
                 @click="gestioTeaPlan(plan)">
                 <!--he canviat  @selected="handleSelectCoffeePlan"
                 por el el @click ja que el emit envia la info automaticamente-->
        </TeaPlan2>

    </div>
</template>