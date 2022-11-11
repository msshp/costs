<template>
  <div id="app">
    <button v-on:click="clicked = !clicked">ADD NEW COST +</button>
    <expensesList v-bind:information="list"></expensesList>
    <expensesAddForm v-on:addNewPayment="addNewPayment" v-show="clicked"></ExpensesAddForm>
  </div>
</template>

<script>
import ExpensesAddForm from './components/expensesAddForm.vue'
import expensesList from './components/expensesList.vue'

export default {
  name: 'App',
  components: {
    expensesList,
    ExpensesAddForm
  },
  data() {
    return {
      list: [],
      clicked: false
    }
  },
  created() {
    setTimeout(() => {
      this.list = [
        { date: '23.10.2022', category: 'food', value: 340 },
        { date: '24.10.2022', category: 'clothes', value: 1000 },
        { date: '25.10.2022', category: 'food', value: 200 },
      ]
    }, 1000)
  },
  methods: {
    addNewPayment(data) {
      this.list = [...this.list, data]
    }
  }
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;

  button {
    padding: 10px 20px;
    background-color: rgb(230, 226, 221);
    border-radius: 5px;
  }
}
</style>
