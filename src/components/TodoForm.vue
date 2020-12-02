<template>
  <form @submit.prevent="formulario">
      <input 
      type="text"
      class="form-control my-3"
      placeholder="Ingrese tarea"
      v-model.trim="texto"
      >
  </form>
</template>

<script>
import { inject, ref } from 'vue'
export default {
    setup(){
        const todos = inject('todos')
        const texto = ref('')
        const formulario = () =>{
            //console.log(texto.value)
            if( texto.value===''){
                console.log('Esta vacío')
                return
            }
            
            const todo = {
                texto:texto.value,
                estado:false,
                id: Date.now(),
            }
            todos.value.push(todo)

            texto.value = ''
            console.log(todos.value)
            
        }
         return {formulario, texto}
        
    }
}
</script>

<style>

</style>