<template>
    Todos
    <button @click="addTodo">Add Todo</button>
    <h1>All</h1>
    <ul>
        <single-todo
        v-for="todo in todos" 
        :key="todo.id"
        :todo="todo"
        />
    </ul>
    <h1>Pending</h1>
    <ul>
        <single-todo
        v-for="todo in pending" 
        :key="todo.id"
        :todo="todo"
        />
    </ul>
    <h1>Completed</h1>
    <ul>
        <single-todo
        v-for="todo in completed" 
        :key="todo.id"
        :todo="todo"
        />
    </ul>
</template>
<script>
import { useTodoStore } from '../stores/TodoStore';
import { mapState } from 'pinia';
import SingleTodo from "../components/SingleTodo.vue";
export default {
    name:'HomePage',
    components: {SingleTodo},
    data() {
        return {}
    },
    computed: {
        ...mapState(useTodoStore, {
            todos: "allTodos",
            pending: "pendingTodos",
            completed: "completedTodos",
        }),
    },
    methods: {
        addTodo() {
            useTodoStore().addTodo({
                id: this.todos.length+1,
                title: "Todo " + (this.todos.length+1),
                completed:false
            })
        }
    },
    
}
</script>