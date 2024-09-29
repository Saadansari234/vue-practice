<template>
    <h1>hello from todo list</h1>
    <div class="container">
        <div class="row">
            <p class="display-3">Todo List</p>
            <div class="col-12 col-lg-6">
                <ul>
                    <Todo v-for="(todo, index) in todos" :key="index" :todoString="todo.todoString" :completed="todo.completed" />
                </ul>
            </div>
        </div>
    </div>
</template>

<script>
        import Todo from "./Todo.vue"
    export default {
        components:{
        Todo
        },
        data() {
            return {
                todos: [
                    { todoString: "make a coffe", completed: false },
                    { todoString: "make a program", completed: true },
                    { todoString: "make a project", completed: true },
                    { todoString: "make a tea", completed: false },
                ]
            }
        },
        methods: {
            addtodo(newtodo) {
                this.todos.push({
                    todoString: newtodo, completed: false
                })
            },
            toggletodo(todo) {
                todo.completed = !todo.completed
            },
            edittodo(todo, newtodoString) {
                todo.todoString = newtodoString
            },
            deletetodo(deletedtodo) {
                this.todos = this.todos.filter(todo => todo.todoString !== deletedtodo.todoString)
            },

        }
    }
</script>

<style>

</style>