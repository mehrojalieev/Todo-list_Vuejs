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
        <!-- <TodoItemWrapper/> -->
    </div>
</template>


<style lang="scss" scoped>
    .todo-wrapper{
        margin: 20px auto 0;
        max-width: 630px;
        height: 635px;
        overflow: hidden;
        border-radius: 10px;
        box-shadow: rgba(0, 0, 0, 0.35) 0px 5px 15px;
    }
</style>