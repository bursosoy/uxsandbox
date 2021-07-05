<template>
  <div>
    <button @click="eatBurger(burgerSettings)">eat burger!</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      burgerSettings: { // payload
          meatType: 'beef', 
          color: 'brown', 
          qty: 10
          }
    }
  },
  methods: {
    eatBurger(payload) {
      console.log(payload.meatType)
      console.log(payload.color)
      console.log(payload.qty)
    },
  },
}
</script>

<style lang="scss" scoped>
div,
button {
  font-size: 1.5rem;
}
</style>
