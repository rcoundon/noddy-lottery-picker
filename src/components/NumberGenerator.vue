<template>
  <div class="container">
    <b-field label="Lottery Numbers">
      <b-input size="is-large" :value="numbers[0] || undefined"></b-input>
      <b-input size="is-large" :value="numbers[1] || undefined"></b-input>
      <b-input size="is-large" :value="numbers[2] || undefined"></b-input>
      <b-input size="is-large" :value="numbers[3] || undefined"></b-input>
      <b-input size="is-large" :value="numbers[4] || undefined"></b-input>
      <b-input size="is-large" :value="numbers[5] || undefined"></b-input>
    </b-field>
    <b-button type="is-primary" @click="generateRandomNumbers"
      >Generate!</b-button
    >
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
      Vue.set(this.numbers, 0, generateRandomNumber(this.numbers));
      Vue.set(this.numbers, 1, generateRandomNumber(this.numbers));
      Vue.set(this.numbers, 2, generateRandomNumber(this.numbers));
      Vue.set(this.numbers, 3, generateRandomNumber(this.numbers));
      Vue.set(this.numbers, 4, generateRandomNumber(this.numbers));
      Vue.set(this.numbers, 5, generateRandomNumber(this.numbers));
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
