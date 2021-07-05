<template>
  <div>Parent parentFood: {{ parentFood }}</div>
  <main-child :parentFood="parentFood" @mainChildShout="accepted"></main-child>
  <!-- <button @click="parentFood = 'tomato'">Change food</button> -->
</template>

<script>
export default {
  data() {
    return {
      parentFood: 'pasta',
    }
  },
  components: {
    'main-child': require('../components/DeepPropEmit/mainChild').default,
  },
  methods:{
      accepted(payload){
          console.log('accepted from mainChild '+payload)
          this.parentFood = payload
      }
  }
}
</script>

<style lang="scss">
div {
  font-size: 2rem;
}
</style>
