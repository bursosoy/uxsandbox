<template>
  <div v-for="fruit in fruits" :key="fruit">
    {{ fruit.name }}:{{ fruit.taste }}
  </div>
</template>

<script>
// "for" in development => it means loop
// x = 0
// x = 1
//....
// x = 9

export default {
  data() {
    return {
      fruits: [
        {name: "apple", taste: "sweet"},
        {name: "orange", taste: "sour"},
        {name: "grapes", taste: "sour"}
        ]
    }
  },
  methods: {
    // outputNumber(){
    //   for(let x=0; x<10; x++){ // Javascript for loop
    //     console.log("kiyu"+x)
    //   }
    // }
  },
}
</script>

<style lang="scss">
div {
  font-size: 2rem;
}
</style>
