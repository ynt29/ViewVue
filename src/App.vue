<template>
  <div class="main">
    <todoList :todoItems="todoItems"></todoList>
    <input type="text" v-model="text">
  </div>
</template>

<script>
import todoList from './components/todoList.vue'

export default {
  name: "Main",
  components: {todoList},
 
  computed: {
    sortItem () {
      return this.todos.slice(0).sort((a, b) => {b.time - a.time})
      }
  },
  methods: {
    save () {
      alert('save')
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
      todos: [
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
        },
      ],
    };
  },
};
</script>

<style>
.main {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: white;
  background-color: black;
  margin-top: 60px;
}

.red {
  color: crimson;
}
.green {
  color: green;
}
</style>
