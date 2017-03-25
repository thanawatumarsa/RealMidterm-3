<template>
<div id="app" class="container">
  <div class="page-header">
    <h1><div style="float: right;"> {{number}} </div></h1><br><br>
    <h3><div style="float: right;" v-if="show"> -{{sumtext}}% </div></h3><br>
    <h2><div style="float: right;"> {{total}} </div></h2><br><br>
  </div>
  <div class="page-header">
    <button class="btn btn-default btn-lg" :disabled="number == ''" @click="discount(10)">10%</button>
    <button class="btn btn-default btn-lg" :disabled="number == ''" @click="discount(20)">20%</button>
    <button class="btn btn-default btn-lg" :disabled="number == ''" @click="discount(30)">30%</button>
    <br><br>
    <button class="btn btn-default btn-lg" :disabled="number == ''" @click="discount(40)">40%</button>
    <button class="btn btn-default btn-lg" :disabled="number == ''" @click="discount(50)">50%</button>
    <button class="btn btn-default btn-lg" :disabled="number == ''" @click="discount(60)">60%</button>
    <br><br>
  </div>
  <button class="btn btn-default btn-lg" @click="addNumber(7)">7</button>
  <button class="btn btn-default btn-lg" @click="addNumber(8)">8</button>
  <button class="btn btn-default btn-lg" @click="addNumber(9)">9</button>
  <br><br>
  <button class="btn btn-default btn-lg" @click="addNumber(4)">4</button>
  <button class="btn btn-default btn-lg" @click="addNumber(5)">5</button>
  <button class="btn btn-default btn-lg" @click="addNumber(6)">6</button>
  <br><br>
  <button class="btn btn-default btn-lg" @click="addNumber(1)">1</button>
  <button class="btn btn-default btn-lg" @click="addNumber(2)">2</button>
  <button class="btn btn-default btn-lg" @click="addNumber(3)">3</button>
  <br><br>
  <button class="btn btn-default btn-lg" @click="clear()">c</button>
  <button class="btn btn-default btn-lg" @click="addNumber(0)">0</button>
  <button class="btn btn-default btn-lg" @click="remove()"><</button>
  <br><br>
</div>
</template>

<script>
export default {
  name: 'app',
  data() {
    return {
      number: '',
      sumtext: 0,
      sum: 0,
      total: '',
      show: false
    }
  },
  methods: {
    addNumber(number) {
      this.number += number
    },
    discount(pernum) {
      this.sum = (this.number * pernum) / 100
      this.total = this.number - this.sum
      this.sumtext = pernum
      this.show = true
    },
    clear() {
      this.sum = ''
      this.total = ''
      this.sumtext = ''
      this.number = ''
      this.show = false
    },
    remove() {
      this.number = this.number.substring(0, this.number.length - 1)
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
  color: #2c3e50;
  margin-top: 60px;
}
</style>
