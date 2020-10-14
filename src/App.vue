<template>
  <div id="app">
    <div class="container">
      <button :class="{ selected : isSelected }" @click="isSelected = !isSelected">bouton 1</button>
      <button @click="toggle">bouton 2</button>
      <button @click="toggle($event, selected)">bouton 3</button>
    </div>
  </div>
</template>

<script>

export default {
  name: 'App',
  data() {
    return {
      isSelected: false
    }
  },
  methods: {
    toggle(event) {
      event.target.classList.toggle('selected');
    },
    toggleAdvanced(event, theClass){
      event.target.classList.toggle(theClass);
    }
  }
}
</script>

<style>
/*===== BASE =====*/
*,::before,::after{
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  background-color: #EEE;
  font-family: sans-serif;
}

.container {
  margin: 20px auto;
  width: 1200px;
  padding: 20px;
  display: flex;
  justify-content: space-around;
}

.container button {
  padding: 10px 20px;
  background-color: red;
  color: #fff;
  border: 1px solid red;
  border-radius: 4px;
  cursor: pointer;
}

.container button:focus {
  outline: none;
}

.container button.selected {
  background-color: green;
  border: 1px solid green;
}
</style>
