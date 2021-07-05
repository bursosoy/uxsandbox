<template>
  <div>{{ ageToForty }}</div>
</template>

<script>
export default {
    data(){
        return{
            firstName: 'Kiyu',
            lastName: 'Tran',
            age: 30,
        }
    },
    computed:{ //its like method but must always return
    // computed is lightweight (its not heavy on computer RAM and speed and internet and processing)
        fullName(){
            return this.lastName + " " + this.firstName
        },
        ageToForty(){
            return (40 - this.age) > 20 ? '20 years or more' : 'less than 20 years'
        }
    }
}
</script>

<style>
div{font-size: 2rem;}
</style>