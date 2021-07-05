<template>
  <div class="game-wrap">
    <div>{{ games[0].name }}</div>
    <div class="image">111</div>
    <div class="desc">{{ games[0].desc }}</div>
    <div class="rating">Rating: {{ games[0].rating }}</div>
  </div>
</template>

<script>
export default {
  props: {
    games: Array,
  },
}
</script>

<style lang="scss" scoped>
.game-wrap {
  display: inline-flex;
  flex-direction: column;
  background-color: lightblue;
  padding: 1rem;
  border-radius: 0.5rem;
  min-width: 12rem;

  .image {
    height: 8rem;
    background-color: rgb(146, 193, 209);
    margin: 1rem 0;
  }

  .desc {
    max-width: 10rem;
    font-size: 0.8rem;
    margin-bottom: 1rem;
  }

  .rating {
    font-size: 1rem;
  }
}
</style>
