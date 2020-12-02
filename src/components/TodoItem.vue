<template>
  <li class="list-group-item d-flex justify-content-between align-items-center">
      <span role="button">{{todo.texto}} </span> 
      <span role="button" @click="eliminar(todo.id)"><i class="fas fa-times"></i></span>
        </li>
</template>

<script>
import { inject } from 'vue'
export default {
    props:{
        todo:{
            type: Object,
            required: true
        },
        setup(){
            const todos     = inject('todos')  

            const eliminar  = id => {
                todos.value = todos.value.filter( item => item.id !== id )
            }
            
            return {eliminar}
        }
     
    }
}
</script>

<style>

</style>