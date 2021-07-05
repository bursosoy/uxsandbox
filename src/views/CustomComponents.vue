<template>
  <div>
    <custom-label :expectedWord="labelWord"></custom-label>
    <custom-button :expectedLabel="buttonLabel" @changeLabel="doThis"></custom-button>
  </div>
</template>

<script>
import CustomButton from '../components/custom/button'
import CustomLabel from '../components/custom/label'
export default {
  data() {
    return {
      buttonLabel: 'Login',
      labelWord: 'Promotions'
    }
  },
  components: {
    'custom-button': CustomButton,
    'custom-label': CustomLabel,
  },
  methods:{
      doThis(value){
          this.labelWord = value
      }
  }
}
</script>

<style>
div,
button {
  font-size: 2rem;
}
</style>
