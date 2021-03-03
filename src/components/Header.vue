<template>
  <header>
    <h1>{{title}}</h1>
    <Button 
      :text="showAddTask ? 'Close' : 'Add Task'" 
      :color="showAddTask ? 'red' : 'green'"
      @btn-click="$emit('btn-click')"/>
  </header>
</template>

<script>
import Button from './Button'

export default {
  name: 'Header',
  // props: ['title']
  props: {
    title: String,
    showAddTask: Boolean
  }, 
  // props: {
  //   title: {
  //     type: String,
  //     default: "Hello World!"
  //   }
  // }
  components: {
    Button
  },
  emits: ['btn-click'] 
}
</script>

<style scoped>
  header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 20px;
  }
</style>