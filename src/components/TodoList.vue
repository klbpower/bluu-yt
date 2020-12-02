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
    </ul>
</template>

<script>
import { inject } from 'vue'
import TodoItem from './TodoItem.vue'
import TodoFooter from './TodoFooter.vue'
export default {
  components: { TodoItem, TodoFooter },
  setup(){
      const todos = inject('todos')

      return{todos}
  }
}
</script>

<style>

</style>