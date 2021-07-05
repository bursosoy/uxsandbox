<template>
  <div>SubChild childFood: {{ childFood }} <button @click="shout">Change to Potato</button></div>
</template>

<script>
export default {
    data(){
        return{
            food: 'pizza'
        }
    },
  props: ['childFood'],
  emits: ['subChildShout'],
  methods: {
    shout() {
      const food = 'potato'
      this.$emit('subChildShout', food)
    },
    whisper() {
      const food = 'carrot'
      this.$emit('subChildShout', food)
    },
  },
}
</script>

<style></style>
