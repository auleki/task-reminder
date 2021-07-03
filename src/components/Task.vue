<template>
  <div :class="[task.reminder ? 'reminder' : '', 'task']">
    <div class="task__title">
      <h5>{{ task.text }}</h5>
      <i @click="deleteTask(task.id)" class="fas fa-times"></i>
    </div>
    <p>{{ task.day }}</p>
  </div>
</template>

<script>
export default {
  name: 'Task',
  props: {
    task: Object
  },
  methods: {
    deleteTask (id) {
      this.$emit('delete-task', id)
    }
  }
}
</script>

<style scoped>
  .fas {
    color: red;
    cursor: pointer;
    font-size: 1.2em;
    transition: 200ms ease-in;
  }

  .fas:hover {
    color: #fff;
    transform: rotateZ(180deg);
  }

  p {
    color: rgb(197, 197, 197);
  }

  .task {
    background: rgb(17, 17, 17);
    color: rgb(255, 255, 255);
    padding: 1em;
    border-left: solid transparent 3px;
    margin: 1em 0;
    border-radius: .3em;
  }

  .reminder {
    border-color: rgb(255, 136, 0);
  }

  .task__title {
    display: flex;
    justify-content: space-between;
  }

  h3 {
    display: inline;
  }
</style>