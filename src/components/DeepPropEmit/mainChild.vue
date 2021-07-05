<template>
  <div>Child parentFood: {{ parentFood }}</div>
  <sub-child :childFood="parentFood" @subChildShout="accepted"></sub-child>
</template>

<script>
export default {
  props: ['parentFood'],
  components: {
    'sub-child': require('./subChild').default,
  },
  methods:{
    accepted(payload){
      console.log('accepted from subChild')
      this.$emit('mainChildShout', payload)
    }
  },
  emits:['mainChildShout']
}
</script>

<style></style>
