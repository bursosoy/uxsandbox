<template>
  <div>
    <input v-model="person.name" type="text" />
    <input v-model="person.age" type="text" />
    <button @click="checkName">check the name</button>
    <div>{{ person }}</div>

    <input type="checkbox" id="vehicle1" name="vehicle1" value="Bike" v-model="person.isBike" />
    <label for="vehicle1"> I have a bike</label><br />
  </div>
</template>

<script>
export default {
  data() {
    return {
      name: '',
      person: {
        name: '',
        age: '',
        isBike: false,
      },
    }
  },
  methods: {
    checkName() {
      console.log(this.name)
    },
  },
}
</script>

<style>
div,
input,
button {
  font-size: 2rem;
}
</style>
