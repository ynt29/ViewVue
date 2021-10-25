<template>
    <ul>
        <li v-for="todo in todoItems" :key="todo.time"
        :class="{red: todo.completed, green: todo.completed}">
        {{todo.text}}
        </li>
    </ul>
</template>

<script>
export default {
    name: 'todoList',
    props: {
        todoItems: {
            type: Array
        }
    },
    mounted () {
        console.log(this.todoItems)
    }
}

</script>

<style>

</style>