<template>
  <div class="container">
    <b-field>
      <b-input :value="numbers[0]"></b-input>
      <b-input :value="numbers[1]"></b-input>
      <b-input :value="numbers[2]"></b-input>
      <b-input :value="numbers[3]"></b-input>
      <b-input :value="numbers[4]"></b-input>
      <b-input :value="numbers[5]"></b-input>
    </b-field>
    <b-button @click="generateRandomNumbers">Generate!</b-button>
  </div>
</template>

<script>
import Vue from 'vue';
function generateRandomNumber(existingNumbers) {
  let min = 1;
  let max = 59;
  min = Math.ceil(min);
  max = Math.floor(max);
  let result = Math.floor(Math.random() * (max - min) + min);
  if (existingNumbers.includes(result)) {
    return generateRandomNumber(existingNumbers);
  } else {
    return result;
  }
}
export default {
  name: 'HelloWorld',
  data() {
    return {
      numbers: [0, 0, 0, 0, 0, 0],
    };
  },
  methods: {
    generateRandomNumbers() {
      let number0 = generateRandomNumber(this.numbers);
      let number1 = generateRandomNumber(this.numbers);
      let number2 = generateRandomNumber(this.numbers);
      let number3 = generateRandomNumber(this.numbers);
      let number4 = generateRandomNumber(this.numbers);
      let number5 = generateRandomNumber(this.numbers);
      Vue.set(this.numbers, 0, number0);
      Vue.set(this.numbers, 1, number1);
      Vue.set(this.numbers, 2, number2);
      Vue.set(this.numbers, 3, number3);
      Vue.set(this.numbers, 4, number4);
      Vue.set(this.numbers, 5, number5);
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
