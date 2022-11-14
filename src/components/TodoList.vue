<template>
    <todo-item v-for="task in taskList" :key="task" :taskItem="task"></todo-item>
</template>

<script>
    import TodoItem from './TodoItem.vue'
    export default {
        props:['taskList'],
        // created() {
        //     // props are exposed on `this`
        //     console.log(this.taskList, '1')
        // },
        components: {
            TodoItem
        }
    }
</script>
