<template>
    <ul class="todo-main">
        <TodoItem v-for="todoObj in todos" :key="todoObj.id" :todoObj="todoObj"></TodoItem>
    </ul>
</template>

<script>
    import TodoItem from './TodoItem'

    export default {
        name: "TodoList",
        components: {TodoItem},
        data() {
            return {
                "todos": [
                    {id: "001", title: "抽烟", complete: true},
                    {id: "002", title: "喝酒", complete: false},
                    {id: "003", title: "吃肥肉", complete: true}]
            }
        }
    }
</script>

<style scoped>
    /*main*/
    .todo-main {
        margin-left: 0px;
        border: 1px solid #ddd;
        border-radius: 2px;
        padding: 0px;
    }

    .todo-empty {
        height: 40px;
        line-height: 40px;
        border: 1px solid #ddd;
        border-radius: 2px;
        padding-left: 5px;
        margin-top: 10px;
    }
</style>