<template>
  <button>Submit</button>
</template>

<script>
export default {

}
</script>

<style lang="scss" scoped>
button{
    font-family: Source Sans Pro;
    padding: 1rem 2rem;
    margin: 1rem;
    outline: none;
    border: none;
    border-radius: 2rem;
    font-size: 1.5rem;
    font-weight: bold;
    background-color: lightcoral;
    cursor: pointer;

    transition: transform 0.1s, background-color 0.1s, padding 0.1s;
    transition-timing-function: ease-in;

    &:hover{
        transform: scale(1.07);
        background-color: lightblue;
        padding: 1rem 3rem;
    }
}
</style>