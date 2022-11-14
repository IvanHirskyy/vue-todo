<script>
import CreateTodo from './CreateTodo.vue'
import TodoList from './TodoList.vue'

export default {
    components: {
        CreateTodo,
        TodoList
    },
    data() {
        return {
            tasks: []
        }
    },
    methods: {
        createTask(task) {
            this.tasks.push(task)
            localStorage.setItem('tasks', JSON.stringify(this.tasks));
        }
    },
    mounted: function () {
        const existingTasks = localStorage.getItem('tasks');
        this.tasks = JSON.parse(existingTasks) || [];

        console.log('mounted', this.tasks);
    }
}
</script>

<template>
    <create-todo @sendTaskData="createTask"></create-todo>
    <todo-list :taskList="tasks"></todo-list> 
</template>