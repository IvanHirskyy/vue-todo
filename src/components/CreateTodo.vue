<template>
    <form @submit.prevent="sendTask">
        <h1>Todo</h1>
        <input type="text" v-model="task.name" placeholder="What needs to be done ?">
        <br>
        <p>Pessoal</p>
        <input type="radio" name="type" value="0" v-model="task.type">
        <br>
        <p>Profissional</p>
        <input type="radio" name="type" value="1" v-model="task.type">
        <br>

        <button type="submit">Adicionar</button>
    </form>
</template>

<script>
export default {
    data() {
        return {
            task: {
                name: '',
                type: '',
                status: false
            }
        }
    },
    methods: {
        sendTask() {
            this.$emit('sendTaskData', {
                name: this.task.name, 
                status: this.task.status, 
                type: this.task.type
                
            })
        }
    }
}
</script>