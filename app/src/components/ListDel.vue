<template>
    <div>
        <ul>
            <Dela 
           v-for="todo of todoes"
            v-bind:key="todo"
            v-on:remove-todo="removeTodo"
            />
        </ul>
    </div>
</template>

<script>
import Dela from '@/components/Dela'
export default {
    props:['todos'],
      components:{
          Dela
    },
    methods: {
        removeTodo(id){
            this.$emit('remove-todo', id)
            console.log(id)
        }
    }
}
</script>

<style scoped>
ul{
    list-style: none;
    margin: 0;
    padding: 0;
}
</style>