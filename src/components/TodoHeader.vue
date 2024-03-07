<script>
import TodoItemWrapper from '@/components/TodoItemWrapper.vue'
    export default {
        components:{TodoItemWrapper},
        data(){
            return {
                All_Task: [],
                    input_value: ''
            }
        },
        methods: {
            handleAddTask(e){
                const taskData = {  task_name: this.input_value }
                if(this.input_value.trim().length > 0){
                    this.All_Task.unshift(taskData);
                    console.log(this.All_Task);
                    this.input_value = ''
                }  
                else{
                    alert("Please, Add a new task !")
                }
            }
        }
    }
</script>

<template>
    <div class="todo__header-wrapper">
            <h1>TODO List</h1>
            <form @submit.prevent="handleAddTask" class="add__task-form">
                <input v-model="input_value" placeholder="What would you like to do ? "/>
                <button type="submit">Add</button>
            </form>
    </div>
    <TodoItemWrapper :All_Task="All_Task"/>
</template>

<style >
    .todo__header-wrapper{
        width: 100%;
        height: 140px;
        background-color: #5d4d8a;
        text-align: center;
        position: relative;
        h1{
            display: inline-block;
            color: #fff;
            line-height: 5px;
            font-size: 26px;
            letter-spacing: .5px;
            font-weight: 500;
            font-family: system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
        }

        .add__task-form{
            padding: 1rem 3rem;
            background-color: #fff;
            box-shadow: rgba(0, 0, 0, 0.24) 0px 3px 8px;
            width: 100%;
            max-width: 500px;
            height: 135px;
            margin: auto;
            border-radius: 10px;
            display: grid;
            place-items: center;
            position: absolute;
            top: 40%;
            left: 2.4%;
            input{
                width: 100%;
                border: none;
                outline: none;
                border-bottom: 2px solid gray;
                font-size: 20px;
                padding-bottom: 4px;
            }
            button{
                padding: 6px 70px;
                font-size: 18px;
                color: #fff;
                border: none;
                border-radius: 5px;
                background-color: #ED6A5A;
                transition: 0.2s;
                &:hover{
                    opacity: 0.8;
                    cursor: pointer;
                }
                &:active{
                    transform: scale(0.98);
                }
            }
        }
    }
</style>