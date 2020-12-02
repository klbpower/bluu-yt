<template>
    <h1>Todo app</h1>
    <todo-form />
    <todo-list/>
</template>


<script>
import { provide, ref, watchEffect } from 'vue'
import TodoForm from './TodoForm.vue'
import TodoList from './TodoList.vue'

export default {
  components: { TodoForm, TodoList },
  setup(){
      const todos = ref( [] )
      provide( 'todos', todos ) 
      watchEffect(()=> {
          console.log( todos.value.length )
          console.log( todos.value )
      })

  } 
}
</script>

<style>

</style>