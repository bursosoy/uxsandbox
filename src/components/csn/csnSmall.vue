<template>
  <div class="game-wrap">
      <div>{{ games[0].name }}</div>
      <div class="image">111</div>
      <div class="rating">Rating: {{ games[0].rating }}</div>
  </div>
</template>

<script>
export default {
    props:{
        games: Array
    }
}
</script>

<style lang="scss" scoped>
.game-wrap{
    display: inline-flex;
    flex-direction: column;
    background-color: lightcoral;
    padding: 1rem;
    border-radius: 0.5rem;

    .image{
        height: 4rem;
        background-color: rgb(218, 107, 107);
        margin: 1rem 0;
    }

    .rating{
        font-size: 1rem;
    }
}
</style>