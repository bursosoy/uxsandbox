<template>
  <!-- <div>anyNumber: {{ anyNumber }}</div>
  <div>anyString: {{ anyString }}</div>
  <div>anyBoolean: {{ anyBoolean }}</div>
  <div>anyArray at 1: {{ anyArray[1] }}</div>
  <div>anyObject color: {{ anyObject.color }}</div>

  <div v-if="anyNumber === 0 && anyBoolean === false">I'm a div</div> -->
  <!-- <div>{{ checkUser("Carlo") }}</div> -->

  <!-- <button @click="logName">Say Name</button>
  <button @click="logNewName('Kiyu')">Say New Name</button> -->
  <!-- <button @click="logNewName(checkUser('Carlo'))">Check User</button> -->
  <div v-if="checkUser('Kiyu') && anyNumber === 0">Show me if its Kiyu!</div>
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
  },
  methods:{
    logName(){ // basic type -> performs tasks
      console.log("Anthony")
      console.log("Dog")
      var myNumber = 1+1
      myNumber = 8
      console.log(myNumber)
    },

    logNewName(newName){ // accepts arguments and passes it to its parameter
      console.log(newName + " Tran")
    },

    logAge(additionalAge){ // accepts argument and returns something
      return additionalAge * 2
    },

    checkUser(name){ // function that returns based on a condition
      if(name === "Kiyu"){
        return true
      }
      else{
        return false
      }
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
