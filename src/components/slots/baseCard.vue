<template>
  <div :class="theme">
    <div>
      <slot name="description"></slot>
    </div>
    <slot name="cta"></slot>
  </div>
</template>

<script>
export default {
    props:{
        theme: String
    }
}
</script>

<style lang="scss" scoped>
.card-wrap {
  display: inline-flex;
  flex-direction: column;
  padding: 2rem;
  background-color: #eee;
  font-family: Source Sans Pro;
  border-radius: 0.5rem;
  max-width: 16rem;
}

.card-wrap-dark {
  display: inline-flex;
  flex-direction: column;
  padding: 2rem;
  background-color: #111;
  color: #eee;
  font-family: Source Sans Pro;
  border-radius: 0.5rem;
  max-width: 16rem;
}
</style>
