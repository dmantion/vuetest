<template>
<li>
    <span v-bindclass="{done: todo.complited}">
        <input type="checkbox" 
        v-on:change="todo.complited = !todo.complited">
        <strong>{{todo.id}}</strong>
        {{todo.title}}
    </span>
    <button class ="rm" v-on:click="$emit('remove-todo', todo.id)"
    >$times;</button>
</li>
</template>

<script>
export default {
  props:{
      todo:{
        type: Object,
        required: true
      }
  }
}
</script>

<style scoped>
li{
    border: 1px solid #ccc;
    display: flex;
    justify-content: space-between;
    padding: .4rem 2rem;
    margin-bottom: 1rem;
}
rm{
    background: red;
    color: #fff;
}
input{
    margin-right: 1rem;
}

.done{
    text-decoration: line-through;
}

</style>