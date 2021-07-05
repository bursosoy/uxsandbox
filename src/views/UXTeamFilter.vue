<template>
  <button @click="isRedShown = !isRedShown">{{ isRedShown ? 'Hide' : 'Show' }} red fishes</button>
  <button @click="isWhiteShown = !isWhiteShown">{{ isWhiteShown ? 'Hide' : 'Show' }} white fishes</button>
  <div v-for="fish in fishList" :key="fish">
    <div v-if="checkState(fish.color)">{{ fish.name }} : {{ fish.color }}</div>
  </div>
  <br /><br /><br /><br /><br />
  <div>
    Is red shown?: {{ isRedShown }} <br>
    Is white shown?: {{ isWhiteShown }}
  </div>
</template>

<script>

// Pure Vuetify => what looks like, and how it behaves in animation
// VueJS + Vuetify => what it looks like, how it behaves, and when it should behave or be shown
// VueX + VueJS + Vuetify => "", easier state management (NO MORE provide/inject, LESSER props!)
// VueRouter + "" => string together different projects (Sandbox => KYC, Login, Promotion)

export default {
  // is member a senior and is Senior shown
  // is fish red and is Red shown

  data() {
    return {
      isRedShown: true,
      isWhiteShown: true,
      fishList: [
        {name: 'salmon', color: 'red'},
        {name: 'tilapia', color: 'red'},
        {name: 'milkfish', color: 'white'},
        {name: 'pompano', color: 'white'},
      ],
    }
  },
  methods: {
    checkState(color) {
      // this returns either true or false
      if (color === 'red' && this.isRedShown === true) {
        return true // if fish color is red, and isRedShown is true, then it must be true
      } else if (color === 'white' && this.isWhiteShown === true) {
        return true // if fish color is white, and isWhiteShown is true, then it must be true
      } else {
        return false
      }
    },
    // checkLabel(state){
    //   if (state === true){
    //     return "Hide"
    //   }else{
    //     return "Show"
    //   }
    // }
  },
}
</script>

<style lang="scss">
div {
  font-size: 1.5rem;
  font-family: Source Sans Pro;
}
</style>
