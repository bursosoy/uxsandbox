<template>
  <button class="orange">{{ label }}</button>
</template>

<script>
export default {
    props:{
        label: String
    }
}
</script>

<style>
.orange{
    padding: 0.5rem;
    background-color: orange;
}
</style>