<template>
  <div class="main">
    <ul>
      <li
        v-for="todo in sortItem"
        :key="todo.time"
        :class="{ red: !todo.completed, green: todo.completed }"
      >
        {{ todo.text }}
      </li>
      <button @click="save()">Save</button>
      
    </ul>
  </div>
</template>

<script>
export default {
  name: "Main",
  watch: {
    todoWatch (oldVal, newVal) {
        console.log(oldVal, newVal)
      }
  },
  beforeCreate() {
    console.log('before create')
  },
  mounted () {
    console.log("mounted!!")
  },
  updated () {

  },
  destroyed() {
    
  },
  computed: {
    sortItem () {
      return this.todos.slice(0).sort((a, b) => {b.time - a.time})
      }
  },
  methods: {
    save () {
      alert('save')
      },
    save2 () {
      this.save()
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
