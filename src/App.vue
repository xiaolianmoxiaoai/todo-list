<template>
  <div id="root">
    <div class="todo-container">
    <div class="todo-wrap">
     <TodoHeader :addTodo="addTodo"></TodoHeader>
      <TodoList :todos="todos" :checkTodo="checkTodo"/>
      <TodoFooter></TodoFooter>
    </div>
  </div>
  </div>
</template>

<script>
import TodoHeader from './components/TodoHeader'
import TodoFooter from "./components/TodoFooter"
import TodoList from "./components/TodoList"

export default {
  name: 'App',
  components: {
    TodoHeader,
    TodoFooter,
    TodoList
  },
    data() {
        return {
            "todos": [
           ]
    }
    },
    methods: {
      // 添加一个todo
      addTodo(todoObj){
          this.todos.unshift(todoObj)
      },
        //勾选或取消勾选一个todo
        checkTodo(id){
          this.todos.forEach((todo)=>{
              if(todo.id === id) todo.complete = !todo.complete
            })
        }
    }
}
</script>

<style>
  /*base*/
  body {
    background: #fff;
  }

  .btn {
    display: inline-block;
    padding: 4px 12px;
    margin-bottom: 0;
    font-size: 14px;
    line-height: 20px;
    text-align: center;
    vertical-align: middle;
    cursor: pointer;
    box-shadow: inset 0 1px 0 rgba(255, 255, 255, 0.2), 0 1px 2px rgba(0, 0, 0, 0.05);
    border-radius: 4px;
  }

  .btn-danger {
    color: #fff;
    background-color: #da4f49;
    border: 1px solid #bd362f;
  }

  .btn-danger:hover {
    color: #fff;
    background-color: #bd362f;
  }

  .btn:focus {
    outline: none;
  }

  .todo-container {
    width: 600px;
    margin: 0 auto;
  }
  .todo-container .todo-wrap {
    padding: 10px;
    border: 1px solid #ddd;
    border-radius: 5px;
  }

</style>
