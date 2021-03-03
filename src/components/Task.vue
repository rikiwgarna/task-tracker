<template>
  <div :class="[task.reminder ? 'reminder' : '', 'task']" @dblclick="$emit('toggle-reminder', task.id)">
    <h3>{{task.text}} <i @click="deleteTask(task.id)" class="fas fa-times"></i> </h3>
    <p>{{task.day}}</p>
  </div>
</template>

<script>

export default {
  name: 'Task',
  props: {
    task: Object
  },
  methods: {
    deleteTask(id) {
      this.$emit('delete-task', id)
    }
  }
}
</script>

<style scoped>
  .task {
    background: #f4f4f4;
    margin: 5px;
    padding: 10px 20px;
    cursor: pointer;
  }

  .task.reminder{
    border-left: 5px solid green;
  }

  .task h3 {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  .fas {
    color: red;
  }
</style>