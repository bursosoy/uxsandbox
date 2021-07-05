// () - parenthesis
// [] - brackets
// {} - curly braces

<template>
  <div>
      <button @click="checkStatus">Run function</button>
      <button @click="checkAge">Check age</button>
  </div>
</template>

<script>
export default {
    data(){
        return{
            status: false,
            age: 1
        }
    },
    methods:{
        checkAge(){
            // normal way
            if(this.age < 10){
                console.log('baby')
            }else if (this.age > 10 && this.age < 20){
                console.log('teens')
            }else{
                console.log('old')
            }

            this.age < 10 
            ? console.log('baby') 
            : this.age > 10 && this.age < 20 
            ? console.log('teens') 
            : console.log('old')
        },
        checkStatus(){
            // normal way
            // if(this.status === true){
            //     this.alertStatus()
            // }else{
            //     this.logStatus()
            // }

            // ternary
            this.status 
            ? this.alertStatus() 
            : this.logStatus()

            // normal way
            // if(this.status === true){
            //     return 'it is true'
            // }else{
            //     return 'it is false'
            // }

            // ternary
            // return this.status === true ? 'it is true' : 'it is false' // if(this.status === true) // is this.status equal to true?
        },
        alertStatus(){
            alert(this.status) // true
        },
        logStatus(){
            console.log(this.status) // false
        }
    }
}
</script>

<style>
div{
    font-size: 2rem;
}
</style>