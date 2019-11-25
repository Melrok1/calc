<template>
  <div id="app">
    <div id="calcWrap">
      <input type="text">
      <div id="buttonWrap">
        <button>7</button>
        <button>8</button>
        <button>9</button>
        <button>+</button>
        <button>4</button>
        <button>5</button>
        <button>6</button>
        <button>-</button>
        <button>1</button>
        <button>2</button>
        <button>3</button>
        <button>*</button>
        <button>C</button>
        <button>0</button>
        <button>.</button>
        <button>/</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      
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
