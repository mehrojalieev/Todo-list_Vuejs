<script>
    export default {
        props: {
            All_Task:{
                type: Array,
                required: true
            }
        },
        data(){
            return {
                isCompleted: false
            }
        },
        methods: {
            DeleteTask(index){
                this.All_Task.splice(index, 1)
            },
            toogleStatus(index){
                this.All_Task[index].completed = !this.All_Task[index].completed
            }
        }

    }
</script>

<template>
    <div class="todo__item-wrapper">
        <div class="item-header">
            <h2>Todo List</h2>
        </div>
        <div class="item__list-header">
            <p>List</p>
            <p>Status</p>
            <p>Close</p>
        </div>
        <div class="item__card-container">
            <div  class="item-card" v-for="(task, index) in All_Task" :key="index">
                <h3>{{task.task_name}}</h3>
                <button @click="toogleStatus(index)">
                        {{ task.completed ? 'Completed'  : 'Pending' }}
                </button>
                <span @click="DeleteTask(index)" class="material-symbols-outlined">delete</span>
            </div>
        </div>
    </div>
</template>

<style>
    .todo__item-wrapper{
        width: 100%;
        max-width: 580px;
        margin:  80px auto 0;
        border-radius: 10px;
            box-shadow: rgba(0, 0, 0, 0.35) 0px 5px 15px;
    }
    .item-header{
        padding: 10px 15px;
        width: 100%;
        h2{
            font-size: 24px;
            font-family: system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
            
        }
    }
    .item__list-header{
        box-sizing: border-box !important;
        display: flex;
        align-items: center;
        padding: 0 15px;
        width: 100%;
        height: 40px;
        justify-content: space-between;
        background-color:  #e9e8e8;
        box-shadow: rgb(50, 50, 93) 0px 50px 100px -20px, rgba(0, 0, 0, 0.3) 0px 30px 60px -30px;
        p{
            font-size: 18px;
            font-weight: 700;
            font-family: "Open Sans", sans-serif;
        }
        p:nth-child(2){
            margin-left: 180px;
        }
    }
    .item__card-container{
        width: 100%;
        max-height: 310px;
        overflow-y: auto;
        &::-webkit-scrollbar{
            appearance: none;
        }
    }
    .item-card{
        margin: 15px 0;
        width: 100%;
        height: 60px;
        display: flex;
        align-items: center;
        justify-content: space-between;
        box-shadow: rgba(100, 100, 111, 0.2) 0px 7px 29px 0px;
        h3{
            font-family: system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
            font-weight: 500;
            font-size: 17px;
            max-width: 200px;
            overflow-x: auto;
            width: 100%;
            padding-left: 15px;
            white-space: nowrap;
            &::-webkit-scrollbar{
                appearance: none;
            }
        }
        button{
            /* margin-left: 20px; */
            background-color: #65d1c3;
            border: none;
            border-radius: 5px;
            color: #fff;
            font-size: 15px;
            padding: 7px 20px;
            transition: 0.1s;
            &:hover{
                cursor: pointer;
                opacity: 0.8;
            }
            &:active{
                transform: scale(0.94);
            }
        }
        span{
            font-size: 24px;
            color: #ff0000;
            cursor: pointer;
            margin-right: 10px;
            transition: .1s;
            &:hover{
                transform: scale(1.1);
            }
            &:active{
                transform: scale(0.94);
            }

        }
    }
</style>