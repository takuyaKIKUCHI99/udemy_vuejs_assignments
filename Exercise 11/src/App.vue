<template>
  <div class="container">
    <div class="row">
      <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
        <h1>Filters & Mixins</h1>
        <h2>With filter</h2>
        <input type="text" v-model="userInput"/>
        <div class="reverse-input">{{userInput | reverse}} ({{userInput | countLength}})</div>
        <hr />
        <h2>With computed</h2>
        <input type="text" v-model="userInput"/>
        <div class="reverse-input">{{ reversedInput }} ({{ countedLength }})</div>
      </div>
    </div>
  </div>
</template>

<script>
import { countedLength } from './countedLength.js';
export default {
  mixins: [countedLength],
  data() {
    return {
      userInput: ''
    }
  },
  filters: {
    reverse(value) {
      return value.split("").reverse().join("");
    }
  },
  computed: {
    reversedInput() {
      return this.userInput.split("").reverse().join("");
    }
  }
};
</script>

<style>
</style>
