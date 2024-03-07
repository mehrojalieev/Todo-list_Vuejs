<script>
import TodoHeader from '@/components/TodoHeader.vue'
import TodoItemWrapper from '@/components/TodoItemWrapper.vue';
export default {
    components: {TodoHeader, TodoItemWrapper}
    
}
</script>

<template>
    <div class="todo-wrapper">
        <TodoHeader/>
    </div>
</template>


<style lang="scss" scoped>
    .todo-wrapper{
        width: 100%;
        width: 630px !important;
        height: 635px;
        overflow: hidden;
        border-radius: 10px;
        background-color: #fff;
        box-shadow: rgba(0, 0, 0, 0.35) 0px 5px 15px;
    }
</style>