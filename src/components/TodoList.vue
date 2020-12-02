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
import { inject } from 'vue'
import TodoItem from './TodoItem.vue'
import TodoFooter from './TodoFooter.vue'
import TodoFiltro from './TodoFiltro.vue'
export default {
  components: { TodoItem, TodoFooter, TodoFiltro },
  setup(){
      const todos = inject('todos')

      return{todos}
  }
}
</script>

<style>

</style>