<template>
  <div>anyNumber: {{ anyNumber }}</div>
  <div>anyString: {{ anyString }}</div>
  <div>anyBoolean: {{ anyBoolean }}</div>
  <div>anyArray at 1: {{ anyArray[1] }}</div>
  <div>anyObject color: {{ anyObject.color }}</div>

  <div v-if="2<1">I'm a div</div>
  <!-- if you want to render it and just hide, use v-show. if you want to save on data loading, use v-if -->
</template>

<script>

export default {
  data(){
    return{
      anyNumber: 0, // Number
      anyString: 'TestString', // String
      anyBoolean: true, // Boolean
      anyArray: ["red","blue","green"], // Array is a container!
      anyObject: {color: "gray"}, // Object

      isDivShown: true // Boolean
    }
  }
}
</script>

<style lang="scss">
body{
  font-family: Alte Haas Grotesk;
  font-size: 1.5rem;
}
</style>
