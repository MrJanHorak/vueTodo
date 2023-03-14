<template>
  <div class="appContainer">
    <h1>To-Do List</h1>

    <input
      v-model="inputValue"
      placeholder="Enter a new task"
      v-on:keyup.enter="onSubmit"
    />

    <ListItem :list="taskArray" />
    <img src="./assets/logo.png" />
  </div>
</template>

<script>
import ListItem from './components/ListItem.vue'

export default {
  name: 'App',
  components: {
    ListItem
  },
  data: () => ({
    inputValue: '',
    index: 0,
    taskArray: []
  }),
  methods: {
    onSubmit() {
      if (this.inputValue === '') {
        return
      }
      console.log('I am submitting: ', this.inputValue)
      this.taskArray.push({ item: this.inputValue, id: this.index })
      console.log(this.taskArray)
      this.index++
      this.inputValue = ''
    }
  }
}
</script>

<style>
html {
  background: linear-gradient(
    22deg,
    rgba(19, 146, 235, 1) 0%,
    rgba(8, 228, 196, 1) 100%
  );
  background-attachment: fixed;
  display: flex;
  flex-direction: column;
  align-items: center;
  align-content: center;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  background-color: white;
  border-radius: 15px;
  width: 70vw;
  display: flex;
  flex-direction: column;
  align-items: center;
  align-content: center;
  box-shadow: rgba(60, 64, 67, 0.3) 0px 4px 4px 4px, rgba(60, 64, 67, 0.15) 0px 5px 8px 8px;
}

img {
  width: 77px;
  height: auto;
  margin: 25px;
}

input {
  width: 58vw;
  height: 55px;
  border-radius: 8px;
  border: 0.5px solid grey;
  font-size: 20px;
  font-weight: bold;
  margin-left: 8px;
  padding-left: 18px;
}

input::placeholder {
  font-size: 20px;
  font-weight: bold;
}

.appContainer {
  display: flex;
  flex-direction: column;
  align-items: center;
  
}
</style>
