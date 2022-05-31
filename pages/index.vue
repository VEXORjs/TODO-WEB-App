<template>
  <main>
    <h1>TO-DO App</h1>
    <p>Create a list of tasks</p>

    <div class="create-new">
      <input
        type="text"
        v-model="newTask"
        placeholder="Add a new task!"
        @keypress.enter="addTask"
      />
      <button @click="addTask">Add</button>
    </div>

    <div class="tasks">
      <Task v-for="(task, i) in $store.state.tasks" :key="i" :task="task" />
    </div>
    <div id="app">
      <p>
        My name is <input v-model="name" />and I am <input v-model="age" />years
        old
      </p>
      <p>
        <button @click="persist">Save</button>
      </p>
    </div>
  </main>
</template>

<script>
const app = new Vue({
  el: '#app',
  data: {
    name: '',
    age: 0,
  },
  mounted() {
    if (localStorage.name) {
      this.name = localStorage.name
    } else if (localStorage.age) {
      this.age = localStorage.age
    }
  },
  methods: {
    persist() {
      localStorage.name = this.name
      localStorage.age = this.age
      console.log('now pretend i did more stuff... ')
    },
  },
})
export default {
  data() {
    return {
      newTask: '',
    }
  },
  methods: {
    addTask() {
      if (this.newTask) {
        this.$store.commit('ADD_TASK', this.newTask)
        this.newTask = ''
      }
    },
  },
}
</script>