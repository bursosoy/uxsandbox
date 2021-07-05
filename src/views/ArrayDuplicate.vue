// () parenthesis // [] brackets // {} curly braces
// string interpolation means to combine strings
// type1: combine each from separate curly braces
// type2: use +
// type3: `${}`
<template>
  <div>
    <input @keydown.esc="fruit = ''" @keydown.enter="addFruit" v-model="fruit" type="text" />
    <button @click="addFruit" style="margin-left: 1rem">Add +</button>
    <div>{{ fruit }}</div>
    <div>{{ fruitList }}</div>
    <div>{{ `${person} ${fruit} very much!` }}</div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      fruitList: [],
      fruit: '',
      person: 'Annie likes'
    }
  },
  methods: {
    addFruit() {
        console.log(`${this.person} ${this.fruit}`)
      if (this.fruitList.includes(this.fruit) === true) {
        alert('Duplicate Item')
      } else {
        this.fruitList.push(this.fruit)
        this.fruitList = this.fruitList.sort()
      }
      this.fruit = '' // DRY don't repeat yourself
    },
  },
}
</script>

<style>
div,
input,
button {
  font-size: 2rem;
  padding: 1rem;
}
</style>
