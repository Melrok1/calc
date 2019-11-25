<template>
  <div id="app">
    <div id="calcWrap">
      <input type="text" v-bind:value="current || 0">
      <div id="buttonWrap">
        <!-- First Row -->
        <button v-on:click="append('7')">7</button>
        <button v-on:click="append('8')">8</button>
        <button v-on:click="append('9')">9</button>
        <button v-on:click="add()">+</button>
        <!-- Second Row -->
        <button v-on:click="append('4')">4</button>
        <button v-on:click="append('5')">5</button>
        <button v-on:click="append('6')">6</button>
        <button v-on:click="minus()">-</button>
        <!-- Third Row -->
        <button v-on:click="append('1')">1</button>
        <button v-on:click="append('2')">2</button>
        <button v-on:click="append('3')">3</button>
        <button v-on:click="multiplication()">*</button>
        <!-- Fourth Row -->
        <button v-on:click="current = ''">C</button>
        <button v-on:click="append('0')">0</button>
        <button v-on:click="equal()">=</button>
        <button v-on:click="divide()">/</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      current: '',
      old: null,
      operator: null,
      operatorClick: false
    }
  },
  methods: {
    append: function(num) {
      if(this.operatorClick) {
        this.current = '';
        this.operatorClick = false;
      }
      this.current = `${this.current}${num}`;
    },

    setOld: function() {
      this.old = this.current;
      this.operatorClick = true;
    },

    add: function() {
      this.operator = (x, y) => x + y;
      this.setOld();
    },

    minus: function() {
      this.operator = (x, y) => x - y;
      this.setOld();
    },

    multiplication: function() {
      this.operator = (x, y) => x * y;
      this.setOld();
    },

    divide: function() {
      this.operator = (x, y) => x / y;
      this.setOld();
    },

    equal: function() {
      this.current = `${this.operator(parseFloat(this.current), parseFloat(this.old))}`;
      this.old = null;
    }
  }
}
</script>

<style>
  * {
    margin: 0px;
    padding: 0px;
    box-sizing: border-box;
  }

  #app {
    display: flex;
    align-items: center;
    justify-content: center;
    height: 100vh;
  }

  #calcWrap {
    display: flex;
    justify-content: stretch;
    align-items: center;
    flex-direction: column;
    width: 40%;
    height: 40%;
    background: rgba(9, 45, 143, 0.767);
    box-shadow: 3px 3px 2px #858585;
  }

  #calcWrap input[type=text]{
    display: block;
    margin: 1rem auto;
    height: 3rem;
    width: 85%;
    padding: 0.25rem 0.5rem;
    font-size: 2rem;
    text-align: right;
  }

  #buttonWrap {
    margin: 0 auto;
    width: 85%;
    min-height: 200px;
    border: 2px solid #a2a2a2;
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    grid-template-rows: repeat(4, 1fr);
  }

  #buttonWrap button {
    font-size: 2rem;
  }
</style>
