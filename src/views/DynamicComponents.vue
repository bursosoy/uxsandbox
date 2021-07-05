<template>
{{ isSmallComp }}
  <button @click="
  isSmallComp = !isSmallComp,
  isSmallComp && (()=> {activeComponent = 'csn-small'})(), // true
  !isSmallComp && (()=> {activeComponent = 'csn-big'})() // false
  ">Switch Game Component</button>
  <br /><br /><br />

  <component :is="activeComponent" :games="games"></component>

</template>

<script>
import csnSmall from '../components/csn/csnSmall.vue'
import csnBig from '../components/csn/csnBig.vue'
export default {
  data() {
      return{
          isSmallComp: true,
          games:[
              {
                  name: "Big Bad Wolf",
                  rating: "5 stars",
                  desc: "I'm a Big Bad Wolf Description"
              }
          ],
          activeComponent: 'csn-small',
      }
  },
  components: {
      'csn-small' : csnSmall,
      'csn-big' : csnBig
    // 'csn-small': require('../components/csn/csnSmall').default,
    // 'csn-big': require('../components/csn/csnBig').default,
  },
  methods:{
  }
}
</script>

<style scoped>
div,
button {
  font-size: 1.4rem;
  font-family: Source Sans Pro;
}
</style>
