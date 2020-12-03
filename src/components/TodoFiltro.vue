<template>
 <div class="card mt-3">
     <div class="card-body d-flex justify-content-between align-items-center">
         <span role="button"
             @click="filtrar('active')"> Activos
         </span>
         <span role="button"
             @click="filtrar('all')"> Todos

         </span>
         <span role="button"
             @click="filtrar('complete')"> Completados
         </span>
     </div>
 </div>
</template>

<script>
import { inject } from 'vue'
export default {
    setup(){ 
        const estado = inject('estado')

        const filtrar = valor => {
            estado.value = valor
        }
        return {filtrar}
    }
}
</script>

<style>

</style>