<template>
  <div id="app">
    <!-- <img class="logo" src="./assets/logo.png">
    <ttt></ttt> -->
    <br> {{ num1 }} {{ operation }} {{ num2 }} = {{ sum }}
    <hr>
    <button @click="add(7)">7</button>
    <button @click="add(8)">8</button>
    <button @click="add(9)">9</button>
    <button @click="hard()">/</button><br>
    <button @click="add(4)">4</button>
    <button @click="add(5)">5</button>
    <button @click="add(6)">6</button>
    <button @click="kun()">x</button><br>
    <button @click="add(1)">1</button>
    <button @click="add(2)">2</button>
    <button @click="add(3)">3</button>
    <button @click="del()">-</button><br>
    <button @click="add(0)">0</button>
    <button @click="total()">=</button>
    <button @click="clear()">C</button>
    <button @click="buk()">+</button>

  </div>
</template>

<script>
// import ttt from './components/Hello' // เรียก hello

export default {
  components: {
    // ttt
  },
  methods: {
    add: function (num) {
      if (this.pass === false) {
        this.num1 += num
        console.log('num1', this.num1)
      } else if (this.pass === true) {
        this.num2 += num
        console.log('num2', this.num2)
      }
    },
    buk: function () {
      this.pass = true
      this.operation = '+'
    },
    del: function () {
      this.pass = true
      this.operation = '-'
    },
    kun: function () {
      this.pass = true
      this.operation = 'x'
    },
    hard: function () {
      this.pass = true
      this.operation = '/'
    },
    total: function () {
      // this.sum = this.num1 + this.num2
      if (this.operation === '+') {
        this.sum = parseInt(this.num1) + parseInt(this.num2)
      } else if (this.operation === '-') {
        this.sum = parseInt(this.num1) - parseInt(this.num2)
      } else if (this.operation === 'x') {
        this.sum = parseInt(this.num1) * parseInt(this.num2)
      } else if (this.operation === '/') {
        this.sum = parseInt(this.num1) / parseInt(this.num2)
      }
    },
    clear: function () {
      this.num1 = ''
      this.num2 = ''
      this.sum = ''
      this.pass = false
      this.operation = ''
    }
  },
  data () {
    return {
      sum: 0,
      num1: '',
      num2: '',
      pass: false,
      operation: ''
    }
  }
}
</script>

<style>
html {
  height: 100%;
}

body {
  display: flex;
  align-items: center;
  justify-content: center;
  height: 100%;
}

#app {
  color: #2c3e50;
  margin-top: -100px;
  max-width: 600px;
  font-family: Source Sans Pro, Helvetica, sans-serif;
  text-align: center;
}

#app a {
  color: #42b983;
  text-decoration: none;
}

.logo {
  width: 100px;
  height: 100px
}
</style>
