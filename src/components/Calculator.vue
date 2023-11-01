<template>
    <div>
      <h1>Kalkulator simpellll</h1>
      <input type="text" v-model="result" disabled>
      <br>
      <div class="buttons">
        <button @click="appendToResult('1')">1</button>
        <button @click="appendToResult('2')">2</button>
        <button @click="appendToResult('3')">3</button>
        <button @click="appendToResult('+')">+</button>
        <br>
        <button @click="appendToResult('4')">4</button>
        <button @click="appendToResult('5')">5</button>
        <button @click="appendToResult('6')">6</button>
        <button @click="appendToResult('-')">-</button>
        <br>
        <button @click="appendToResult('7')">7</button>
        <button @click="appendToResult('8')">8</button>
        <button @click="appendToResult('9')">9</button>
        <button @click="appendToResult('*')">*</button>
        <br>
        <button @click="appendToResult('0')">0</button>
        <button @click="appendToResult('.')">.</button>
        <button @click="clearResult">C</button>
        <button @click="calculateResult">=</button>
        <button @click="appendToResult('/')">/</button>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        result: "",
      };
    },
    methods: {
      appendToResult(value) {
        this.result += value;
      },
      clearResult() {
        this.result = "";
      },
      calculateResult() {
        try {
          this.result = eval(this.result);
        } catch (error) {
          this.result = "Error";
        }
      },
    },
  };
  </script>
  