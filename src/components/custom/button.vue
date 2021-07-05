<template>
  <button @click="emitMyShout('jimmy')">{{ expectedLabel }}</button>
  <button @click="emitMyShout('kleine')">{{ expectedLabel }}</button>
</template>

<script>
export default {
    props:{
        expectedLabel: String
    },
    methods:{
        emitMyShout(name){
            this.$emit('changeLabel', name) // good practice
        }
    },
    emits:['changeLabel'] // informing the whole app that you are going to shout!
}
</script>

<style>

</style>