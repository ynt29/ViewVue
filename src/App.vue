<template>
  <div id="app">
    <Alert>
      <h1 slot="header">Alert Here</h1>
      <h2 slot="text">Text Here</h2>
    </Alert>
    <todoList :todoItems="todoItems"></todoList>
    <InputItem @save="addTodoItem"></InputItem>
  </div>
</template>

<script>
import todoList from './components/todoList.vue'
import InputItem from './components/InputItem.vue'
import Alert from './components/Alert.vue'

export default {
  name: 'app',
  components: {todoList, InputItem},
  methods: {
    addTodoItem (text) {
      this.todoItems.push({
        text: text,
        time: Date.now(),
        completed: false
      })
    }
  },
  filters: {
    capitalize(val) {
      return val.toUpperCase();
    },
  },
  data() {
    return {
       color: "red",
      todoItems: [
        {
          text: "Todo1",
          completed: true,
          time: 1526710200,
        },
        {
          text: "Todo2",
          completed: false,
          time: 1526710200,
        },
        {
          text: "Todo3",
          completed: true,
          time: 1526710200,
        },
        {
          text: "Todo4",
          completed: false,
          time: 1526710200,
        },
        {
          text: "Todo5",
          completed: true,
          time: 1526710200,
        }
      ]
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  background-color:white;
  margin-top: 60px;
}
.red {
  color: crimson;
}
.green {
  color: green;
}

</style>
