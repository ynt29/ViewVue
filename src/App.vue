<template>
  <div class="main">
    <ul>
      <li
        v-for="todo in todos"
        :key="todo.time"
        :class="{ red: !todo.completed, green: todo.completed }"
      >
        {{ todo.text }}
      </li>
      <p>
        {{ text }}
      </p>
      <input type="text" v-model="text" />
    </ul>
  </div>
</template>

<script>
export default {
  name: "Main",
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
