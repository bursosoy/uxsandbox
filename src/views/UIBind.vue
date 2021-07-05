<template>
  <button v-for="game in csnGame" :key="game" :class="'error-message'">{{ game.name }}</button>
  <!-- <div :style="2<1 ? 'background-color: lightcoral' : 'background-color: lightblue'">I'm a div</div> -->
</template>

<script>
export default {
    data(){
        return{
            game: 'adventure',
            csnGame:[
                {name: 'Big Bad Wolf', class:'info'},
                {name: 'Fa Cai Shen', class:'error'},
                {name: 'Adventure Rabbit', class:'success'}
                ]
        }
    },
    methods:{
        isActive(){
            //
            //
            let x = 2
            if (x<1){
                return 'info'
            }else return 'error'
        }
    }
}
</script>

<style lang="scss" scoped>
div, button{
    font-size: 1.5rem;
    font-family: Source Sans Pro;
}

.error-message{
    background-color: lightcoral;
    font-size: 3rem;
}
.success{
    background-color: lightgreen;
    font-size: 2rem;
}

.info{
    background-color: lightblue;
}
</style>