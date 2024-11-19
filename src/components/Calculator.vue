<template>
  <div class="calculator">
    <div class="display">enter value here {{ expression }}</div>
   
    <form @submit.prevent="calculate">
      <div>
        <button type="button" @click.add="expression += '+'">+</button>
        <button type="button" @click.minus="expression += '-'">-</button>
        <button type="button" @click.muitiply="expression += '*'">*</button>
        <button type="button" @click.divide="expression += '/'">/</button>
      </div>
      <div>
        <button type="button" @click.stop="expression += '.'">.</button>
        <button type="button" @click.stop="expression += '9'">9</button>
        <button type="button" @click.stop="expression += '8'">8</button>
        <button type="button" @click.stop="expression += '7'">7</button>
      </div>
      <div>
        <button type="button" @click.stop="expression += '6'">6</button>
        <button type="button" @click.stop="expression += '5'">5</button>
        <button type="button" @click.stop="expression += '4'">4</button>
        <button type="button" @click.stop="expression += '3'">3</button>
      </div>
      <div>
        <button type="button" @click.stop="expression += '2'">2</button>
        <button type="button" @click.stop="expression += '1'">1</button>
        <button type="button" @click.stop="expression += '0'">0</button>
        <button type="submit">=</button>
      </div>
      <div>
        <button type="button" class="clear-button"  @click.stop="expression = ''">Clear</button>
      </div>
    </form>
  </div>
</template>

<script>
import { evaluate } from "mathjs";
export default {
  name: "App",
  data() {
    return {
      expression: "",
    };
  },
  methods: {
    calculate() {
      this.expression = evaluate(this.expression);
    },
  },
};


</script>

<style scoped>
.calculator{
  text-align:center; 
  width:500px;
  height:500px;
  border:1px solid black
}
button {
  width: 70px;
  height: 50px;
  border-radius:100%
}

.clear-button {
  width: 90px;
}

</style>
