<template>
  <button @click="isLight = !isLight">toggle ({{ computedTheme }})</button>
  <br>
  <base-card :theme="computedTheme">
    <template #description>
      <div class="redcontent">{{ longContentR }}</div>
      <div>#summer, #sunlight</div>
    </template>
    <template #cta>
      <div class="textlink">Submit</div>
    </template>
  </base-card>

  <base-card :theme="computedTheme">
    <template #description>
      <div>{{ longContentB }}</div>
    </template>
    <template #cta>
      <base-button label="Read More"></base-button>
    </template>
  </base-card>
</template>

<script>
import baseCard from '../components/slots/baseCard'
import baseButton from '../components/slots/baseButton'
export default {
  data() {
    return {
        isLight: true,
        anyObject:[{name: 'Anthony'}],
        activeComponent: 'base-card',
        longContentR: 'RED Material Design Icons growing icon collection allows designers and developers targeting various platforms to download icons in the format, color and size they need for any project.',
        longContentB: 'BLUE Material Design Icons growing icon collection allows designers and developers targeting various platforms.'
    }
  },
  computed:{
      computedTheme(){
          if(this.isLight === true){
              return 'card-wrap'
          }else{
              return 'card-wrap-dark'
          }
      }
  },
  components: {
    'base-card': baseCard,
    'base-button': baseButton,
  },
  mounted(){ // is a method that runs when you load the page, just once
      console.table(this.anyObject)
  }
}
</script>

<style>
.redcontent {
  color: red;
}
.textlink {
  color: lightcoral;
}

.bluecontent {
  color: blue;
}
.bluebutton {
  background-color: lightblue;
}
</style>
