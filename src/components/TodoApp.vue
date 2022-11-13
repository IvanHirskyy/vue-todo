<script>
export default {
  data() {
    return {
      task: {
        name: '',
        type: '',
        status: false
      },
      tasks: []
    }
  },
  methods: {
    addTask() {
        this.tasks.push({ name: this.task.name, status: this.task.status, type: this.task.type })
        localStorage.setItem('tasks', JSON.stringify(this.tasks));
    }
  },
  mounted: function () {
    const existingTasks = localStorage.getItem('tasks');
    this.tasks = JSON.parse(existingTasks) || [];

    console.log('mounted')
  }
}
</script>

<template>
    <form @submit.prevent="addTask">
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

    <div v-for="task in tasks" :key="task">
        {{task.name}}
        {{task.status}}
        {{task.type}}
    </div>
</template>