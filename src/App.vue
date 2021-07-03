<template>
<div class="container">
  <Header title="Tasks Tracker" />
  <Tasks @delete-task="deleteTask" :tasks="tasks" />
</div>
</template>

<script>
import Header from './components/Header.vue'
import Tasks from './components/Tasks.vue'

export default {
  name: 'App',
  components: {
    Header,
    Tasks
  },
  data () {
    return {
      tasks: []
    }
  },
  methods: {
    deleteTask(id) {
      console.log('task', id)
    }
  },
  created () {
    this.tasks = [
      {
        id: 1,
        text: "Doctor's appointment",
        day: 'June 6th at 3pm',
        reminder: false
      },
      {
        id: 2,
        text: "Wogorowogoro with babe",
        day: 'June 29th at 9pm',
        reminder: true
      },
      {
        id: 3,
        text: "Call Ntongha",
        day: 'June 30th at 1pm',
        reminder: true
      },
      {
        id: 4,
        text: "Make a new application",
        day: 'July 6th at 10pm',
        reminder: true
      },
      {
        id: 5,
        text: "Give tailor new cloth",
        day: 'July 14th at 3pm',
        reminder: false
      }      
    ]
  }
  }
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400&display=swap');
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
body {
  font-family: 'Poppins', sans-serif;
}
.container {
  max-width: 500px;
  margin: 30px auto;
  overflow: auto;
  min-height: 300px;
  border: 1px solid steelblue;
  padding: 30px;
  border-radius: 5px;
}
.btn {
  display: inline-block;
  background: #000;
  color: #fff;
  border: none;
  padding: 10px 20px;
  margin: 5px;
  border-radius: 5px;
  cursor: pointer;
  text-decoration: none;
  font-size: 15px;
  font-family: inherit;
}
.btn:focus {
  outline: none;
}
.btn:active {
  transform: scale(0.98);
}
.btn-block {
  display: block;
  width: 100%;
}
</style>
