<template>
    <ul class="list-group">
        <todo-item 
        v-for="todo in todos" :key="todo.id" 
        :todo="todo"
        />
        <li v-if="todos.length === 0" class="list-group-item">
             No hay elementos
        </li>
       
        <todo-footer >
           
        </todo-footer>
        <todo-filtro />
    </ul>
</template>

<script>
import { computed, inject, provide, ref } from 'vue'
import TodoItem from './TodoItem.vue'
import TodoFooter from './TodoFooter.vue'
import TodoFiltro from './TodoFiltro.vue'
export default {
  components: { TodoItem, TodoFooter, TodoFiltro },
  setup(){
      const tt = inject('todos')
      const estado = ref('all')
      const todos     = computed(( )=> {
          if( estado.value === 'all' ){
              return tt.value
          }else if( estado.value === 'active' ){
              return tt.value.filter( item => item.estado === false )
          }else if( estado.value === 'complete'){
              return tt.value.filter( item => item.estado === true )
          }
    })

    provide('estado', estado) 
    return{todos}
  }
}

</script>

<style>

</style>